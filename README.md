# Fase 6 — Visão Computacional com YOLOv5
### FarmTech Solutions | FIAP — Inteligência Artificial

**Aluno:** Henrique Abreu  
**RM:** 572248  
**Turma:** IA — FIAP 2026

---

## Sobre o Projeto

A FarmTech Solutions expandiu seus serviços de IA para além do agronegócio, atuando agora em saúde animal, segurança patrimonial e visão computacional. Este projeto demonstra o desenvolvimento de um sistema de visão computacional capaz de detectar e classificar objetos em imagens usando o YOLOv5.

**Demo em vídeo:** [Assistir no YouTube ▶](LINK_DO_VIDEO_AQUI)

---

## Estrutura do Repositório

```
.
├── Henrique_Abreu_rm572248_pbl_fase6.ipynb   ← Notebook principal (Entregas 1 e 2)
├── README.md                                  ← Este arquivo
└── assets/                                    ← Prints dos resultados (opcional)
    ├── comparacao_epocas.png
    ├── teste_yolov5_custom.png
    └── cnn_confusion_matrix.png
```

---

## Dataset

- **Classes:** Isqueiro (`isqueiro`) e Carro Miniatura (`carro_miniatura`)
- **Total:** 80 imagens (40 por classe)
- **Distribuição:**

| Conjunto    | Isqueiro | Carro miniatura | Total |
|-------------|----------|-----------------|-------|
| Treino      | 32       | 32              | 64    |
| Validação   | 4        | 4               | 8     |
| Teste       | 4        | 4               | 8     |

As imagens foram fotografadas e rotuladas com o [Roboflow](https://roboflow.com), usando Auto Label com Gemini para geração automática das bounding boxes. O dataset foi exportado no formato YOLOv5 e armazenado no Google Drive.

**Estrutura no Google Drive:**
```
fiap_6_fotos/
  dataset/
    train/
      images/   ← 64 imagens (subpastas por classe)
      labels/   ← arquivos .txt no formato YOLO
    valid/
      images/   ← 8 imagens
      labels/   ← arquivos .txt no formato YOLO
    test/
      images/   ← 8 imagens
```

---

## Como Executar

1. Abra o notebook no Google Colab: **[Henrique_Abreu_rm572248_pbl_fase6.ipynb](Henrique_Abreu_rm572248_pbl_fase6.ipynb)**
2. Faça uma cópia para o seu Drive: `Arquivo > Salvar uma cópia no Drive`
3. Execute as células na ordem (Runtime > Run all)
4. Na célula de montagem do Drive, autorize o acesso

> **Pré-requisito:** as imagens e labels devem estar na pasta `fiap_6_fotos/dataset/` do seu Google Drive conforme a estrutura acima.

---

## Soluções Implementadas

### Entrega 1 — YOLOv5 Customizado

Treinamento do YOLOv5s com fine-tuning no dataset próprio. Dois experimentos foram realizados para comparar o impacto do número de épocas:

- **Experimento 1:** 30 épocas
- **Experimento 2:** 10 épocas

Métricas avaliadas: mAP@0.5, Precision, Recall, Box Loss.

### Entrega 2 — Comparação de Abordagens

| Abordagem | Tipo | Requer rotulação? |
|-----------|------|-------------------|
| YOLOv5 Customizado | Detecção + localização | Sim (bounding box) |
| YOLO Padrão (COCO) | Detecção + localização | Não |
| CNN do Zero | Classificação | Não |

A análise completa com métricas, tempo de treinamento e inferência está no notebook.

---

## Tecnologias

- [YOLOv5](https://github.com/ultralytics/yolov5) — detecção de objetos
- [TensorFlow / Keras](https://www.tensorflow.org/) — CNN do zero
- [Roboflow](https://roboflow.com) — rotulação das imagens (Auto Label com Gemini)
- Google Colab + Google Drive — ambiente de execução e armazenamento

---

*FIAP — Curso de Inteligência Artificial | Fase 6 | 2026*
