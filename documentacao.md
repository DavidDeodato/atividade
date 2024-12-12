# Ponderada

## Identificação de Vulnerabilidades

Durante a análise do projeto, foram identificadas algumas vulnerabilidades que podem comprometer o funcionamento do módulo IoT. Os principais pontos críticos são:

- **Falta de mecanismos de atualização segura**
- **Serviço de rede inseguro**
- **Vulnerabilidades físicas**

---

## Análise das Vulnerabilidades

### Ataque de Firmware Malicioso (Falta de Mecanismos de Atualização Segura)

**Descrição:**  
Um atacante pode comprometer a cadeia de fornecimento, injetando um firmware malicioso no ESP32. Esse firmware pode capturar informações sensíveis, enviá-las para servidores não autorizados ou desativar o dispositivo.

**Pontos Fracos:**
- Servidores mal configurados ou vulneráveis podem ser invadidos, permitindo alterações no firmware na origem.
- Caso a chave privada usada para assinar o firmware seja comprometida, o atacante pode criar firmware malicioso aparentemente legítimo.

---

### Exploração de Comunicação Insegura (Serviço de Rede Inseguro)

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

