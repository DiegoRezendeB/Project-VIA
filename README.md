# Project VIA (Visão Inteligente de Auditoria)

![Badge Flutter](https://img.shields.io/badge/Tecnologia-Flutter-02569B?logo=flutter&logoColor=white)
![Badge AI](https://img.shields.io/badge/AI-TensorFlow_Lite-FF6F00?logo=tensorflow&logoColor=white)
![Badge Status](https://img.shields.io/badge/Status-MVP_Acadêmico-success)

> **VIA:** Um sistema de validação assistida na ponta (Edge AI) para otimizar a auditoria de serviços de campo.

## 📄 Sobre o Projeto

O **Project VIA** é uma Prova de Conceito (PoC) desenvolvida como Trabalho de Conclusão de Curso em Sistemas de Informação. 

O projeto visa modernizar o processo de execução de notas comerciais (WPA) em concessionárias de energia. Atualmente, a coleta de evidências fotográficas em campo sofre com falta de padronização, resultando em retrabalho e dificuldade na auditoria.

O **VIA** propõe uma mudança de paradigma:
1.  **De:** Um formulário aberto e reativo.
2.  **Para:** Um fluxo guiado (Wizard) com **Inteligência Artificial embarcada**, que valida a qualidade da evidência antes mesmo do envio.

## 🎯 Arquitetura da Solução

O sistema utiliza uma abordagem **Híbrida de IA** com validação não-bloqueante ("Soft Validation"):

| Componente | Função | Tecnologia |
| :--- | :--- | :--- |
| **App Mobile** | Interface e Lógica de Negócio | Flutter (Dart) |
| **OCR Engine** | Leitura automática de medidores | Google ML Kit |
| **Scene Detection** | Validação de contexto (ex: "É um medidor?") | Custom Model (TensorFlow Lite) |
| **Backend** | Armazenamento e Sincronização | Firebase (Firestore + Storage) |
| **Treinamento** | Criação do modelo neural | Python + Keras (MobileNetV2) |

## ✨ Funcionalidades Principais

* **🔐 Autenticação Corporativa:** Simulação de login escalonado (Matrícula -> Senha).
* **🔍 Busca Inteligente:** Localização de notas de serviço por ID ou Código de Barras.
* **📋 Checklist Dinâmico:** O app gera as etapas de obrigatoriedade baseadas nos dados da nota (Tipo, Codificação e Grupo de Medidas).
* **🤖 Smart Validation (Edge AI):**
    * Alerta o técnico se a foto estiver borrada ou escura.
    * Verifica se o objeto fotografado corresponde ao solicitado (ex: Medidor vs. Parede).
    * Extrai a leitura do display automaticamente via OCR.
* **📡 Offline-First:** Arquitetura preparada para operar em zonas de sombra (sem sinal).
