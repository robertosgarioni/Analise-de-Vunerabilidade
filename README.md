# Projeto: Laboratório de Pentest no Metasploitable 2 com Kali Linux

## ⚠️ AVISO LEGAL E ÉTICO

**Este projeto é 100% para fins educacionais.**

O objetivo é documentar meu aprendizado em um ambiente de laboratório controlado e isolado. As ferramentas e técnicas aqui demonstradas NUNCA devem ser usadas em redes ou sistemas sem autorização explícita do proprietário. O autor não se responsabiliza pelo mau uso das informações contidas neste repositório.

---

## 🎯 Qual é o objetivo deste repositório?

Bem-vindo! Este repositório é um *walkthrough* pessoal, documentando **passo a passo** a montagem de um laboratório de Pentest. O objetivo é usar o **Kali Linux** como máquina atacante para explorar as vulnerabilidades da famosa VM **Metasploitable 2**.

Aqui você encontrará todo o processo:
* **Configuração:** Montagem das VMs no VirtualBox em uma rede isolada.
* **Reconhecimento:** Descoberta de serviços e portas abertas.
* **Exploração:** Ataques de força bruta e *password spraying* com `medusa` e `hydra`.
* **Validação:** Confirmação dos acessos obtidos.

O resultado é um guia que pode ser facilmente reproduzido, mostrando os comandos, as *wordlists* e a análise de risco de cada falha.

## 💻 O Laboratório (Ambiente e Topologia)

* **Hypervisor:** Oracle VirtualBox
* **VM Atacante:** Kali Linux (IP: `192.168.56.5`)
* **VM Alvo:** Metasploitable 2 (IP: `192.168.56.4`)
* **Rede:** A rede foi configurada como "Host-Only" para garantir que o laboratório ficasse completamente isolado e seguro.

> **💡 Dica de Profissional:** Sempre use *snapshots* no VirtualBox antes de tentar uma nova exploração. Se algo der errado, você pode reverter a VM para um estado limpo em segundos!

---

## 🚀 O Walkthrough: Passo a Passo do Pentest

### Fase 1: Preparação e Reconhecimento

#### 1.1. Teste de Conexão (Sanity Check)

Primeiro, vamos garantir que nossa máquina de ataque (Kali) consegue "enxergar" o alvo (Metasploitable 2). Usamos o bom e velho `ping`.

```bash
# O -c 4 envia 4 pacotes e para.
ping -c 4 192.168.56.4
