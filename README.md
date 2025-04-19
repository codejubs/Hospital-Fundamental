# Hospital Fundamental - Sistema de Gerenciamento Clínico

## Descrição do Projeto

Um hospital local precisa desenvolver um sistema para gerenciar seus dados clínicos e substituir planilhas e arquivos antigos por um banco de dados funcional. O objetivo é criar uma estrutura que registre médicos, pacientes, consultas, convênios, receitas médicas e muito mais.

## Requisitos do Sistema

### Cadastro de Médicos
Alguns registros antigos ainda estão em formulário de papel, mas será necessário incluir esses dados no novo sistema.
- A coleção de médicos, por exemplo, teria suas características definidas como segue:

- _id (ObjectId)
- nome (String)
- data_nascimento (Date)
- especialidades (Array de Strings) - Ex.: ["Pediatria", "Clínica Geral"]
- tipo (String) - Ex.: "Generalista", "Especialista", "Residente"
- contato: { telefone (String), email (String) }
- documentos: { CPF (String), RG (String) }


## Code:
  ```Kt
   "_id": "doc1",
    "nome": "Davi Sandro dos Santos",
    "data_nascimento": "2001.04.26",
    "genero": "masculino",
    "especialidade": "Ortopedista",
    "tipo": "Ortopedia Geral",
    "endereço": {
      "rua/avenida": "Av. Paulista",
      "numero/bloco": "123",
      "complemento": "Apto 101",
      "bairro": "Bela Vista",
      "cidade": "São Paulo",
      "estado": "São Paulo",
      "cep": "64839-403"
    },
    "contato": {
      "telefone": 11985246203,
      "whatsapp": true,
      "email": "davisandro26@hospitalmilu.com",
      "email_pessoal": "davisandrodoc@gmail.com - não mandar emails sobre trabalho!"
    },
    "status": "está em atividade no momento",
    "observação": "está recebendo pacientes",
    "em_atividade": true,
    "documentos": {
      "CPF": "58654123548",
      "CRM": "SP568423",
      "RG": "18934982",
      "digito": "4"
    },
    "agenda": {
      "segunda-feira": "Plantão",
      "terca-feira": "Entre 7h à 19h",
      "quarta-feira": "Entre 8h à 12h",
      "quinta-feira": "Plantão",
      "sexta-feira": "Folga",
      "sabado": "Folga",
      "domingo": "Entre 8h à 18h",
      "feriados": "Folga"
    },
    "plantao": [
      {
        "dia": "Quinta-feira",
        "inicio": "20:00",
        "fim": "14:00"
      },
      {
        "dia": "segunda-feira",
        "inicio": "20:00",
        "fim": "14:00"
      }
    ]
  }

### Cadastro de Pacientes
- Os pacientes também precisam de cadastro, contendo dados pessoais:
  - Nome
  - Data de nascimento
  - Endereço
  - Telefone
  - E-mail
- Documentos:
  - CPF
  - RG
- Convênio:
  - Nome
  - CNPJ
  - Tempo de carência

### Registro de Consultas
- As consultas também têm sido registradas em planilhas, com as seguintes informações:
  - Data e hora de realização
  - Médico responsável
  - Paciente
  - Valor da consulta ou nome do convênio
  - Número da carteira
  - Especialidade buscada pelo paciente

### Receita Médica
- Deseja-se informatizar a receita do médico, de maneira que, no encerramento da consulta, ele possa registrar:
  - Medicamentos receitados
  - Quantidade
  - Instruções de uso
- A partir disso, espera-se que o sistema imprima um relatório da receita ao paciente ou permita sua visualização via internet.

## Conclusão

Este sistema visa melhorar o controle das consultas realizadas e a gestão dos dados clínicos no Hospital Fundamental, proporcionando uma solução moderna e eficiente.
