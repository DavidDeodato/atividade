# Ponderada

## Identificação de Vulnerabilidades

Durante a análise do projeto, foram identificadas algumas vulnerabilidades que podem comprometer o funcionamento do módulo IoT. Os principais pontos críticos são:

- **Falta de mecanismos de atualização segura**
- **Serviço de rede inseguro**
- **Vulnerabilidades físicas**

---

## Análise das Vulnerabilidades

### Ataque de Firmware Malicioso (Falta de Mecanismos de Atualização Segura), (tópico 4 das seções da OWASP):

**Seção:**
Falta de mecanismo de atualização segura, isso inclui a falta de validação do firmware no dispositivo, falta de entrega segura (não criptografada em trânsito), falta de mecanismos anti-rollback e falta de notificações sobre mudanças de segurança devido a atualizações.


**Descrição:**  
Um atacante pode comprometer a cadeia de fornecimento, injetando um firmware malicioso no ESP32. Esse firmware pode capturar informações sensíveis, enviá-las para servidores não autorizados ou desativar o dispositivo.

**Pontos Fracos:**
- Servidores mal configurados ou vulneráveis podem ser invadidos, permitindo alterações no firmware na origem.
- Caso a chave privada usada para assinar o firmware seja comprometida, o atacante pode criar firmware malicioso aparentemente legítimo.

---

### Exploração de Comunicação Insegura (Serviço de Rede Inseguro), (tópico 2 das seções da OWASP)

**Seção:**
Serviços de rede inseguros
Serviços de rede desnecessários ou inseguros em execução no próprio dispositivo, especialmente aqueles expostos à internet, que comprometem a confidencialidade, integridade/autenticidade ou disponibilidade das informações ou permitem controle não autorizado.


**Descrição:**  
Se os dados transmitidos pelo ESP32 não forem criptografados, um atacante pode interceptar ou modificar as informações (ataque man-in-the-middle), comprometendo a integridade do monitoramento.

**Pontos Fracos:**
- Configuração inadequada de protocolos seguros pode causar indisponibilidade de comunicação legítima.
- Certificados TLS vencidos ou mal gerenciados tornam a comunicação suscetível a ataques de downgrade.

---

### Vulnerabilidades Físicas

**Descrição:**  
O acesso físico ao dispositivo pode permitir ataques diretos, como extração de dados, alteração de hardware ou reprogramação maliciosa.

**Pontos Fracos:**
- Falta de proteção física adequada ao dispositivo.
- Possibilidade de acesso não autorizado a portas de comunicação.

---

## Relatório Técnico

### Resumo das Vulnerabilidades
- **Ataque de Firmware Malicioso:** Alto impacto devido à possibilidade de controle total do dispositivo.
- **Exploração de Comunicação Insegura:** Alto impacto devido à interferência direta na confiabilidade dos dados.
- **Vulnerabilidades Físicas:** Impacto moderado devido à necessidade de acesso físico, mas com riscos mitigáveis.

---

## Tabela de Ataques

| **Título do Ataque**              | **Nível de Impacto** | **Nível de Risco** |
|-----------------------------------|----------------------|--------------------|
| Ataque de Firmware Malicioso      | Alto                 | Alto               |
| Exploração de Comunicação Insegura | Alto                 | Alto               |
| Vulnerabilidades Físicas          | Moderado             | Baixo              |

---

### Ataque de Firmware Malicioso

Justificativa para o impacto alto: Firmware malicioso pode comprometer diretamente a funcionalidade do dispositivo, permitindo controle total por um atacante. Isso pode resultar em perda de dados, falha de operação e comprometimento de sistemas críticos.

Justificativa para o risco alto: A dificuldade em detectar alterações no firmware e a possibilidade de instalar um firmware malicioso remotamente tornam este ataque altamente provável e perigoso, aumentando o risco geral.

### Exploração de Comunicação Insegura

Justificativa para o impacto alto: Dados transmitidos de forma insegura podem ser interceptados ou alterados, expondo informações sensíveis e comprometendo a integridade do sistema. Isso pode causar prejuízos financeiros e perda de confiança do usuário.

Justificativa para o risco alto: Muitas vezes, sistemas utilizam padrões de comunicação antigos ou mal configurados, tornando a exploração provável. Adicionalmente, ferramentas para interceptar comunicação são amplamente disponíveis, aumentando o risco.

### Vulnerabilidades Físicas

Justificativa para o impacto moderado: Embora possam causar danos como acessos não autorizados ou roubo de dispositivos, ataques físicos geralmente exigem proximidade ao alvo, limitando o impacto em comparação com ataques remotos.

Justificativa para o risco baixo: Requerem acesso físico ao dispositivo, o que depende de fatores como segurança do ambiente e localização. Isso reduz a probabilidade de ocorrência, resultando em um risco menor.

## Contribuição Individual

| **Nome**         | **Contribuição**                                      |
|-------------------|------------------------------------------------------|
| Cecília | Organização e documentação da ponderada. |
| Daniel | Escreveu o tópico 1. |
| David | Escreveu o tópico 2. |
| Otávio | Organização e documentação da ponderada. |
| Thalyta | Escreveu o tópico 3. |
| Kauan | Escreveu o tópico 1. |
| Milena | Escreveu o tópico 3. |

