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
```

### Cadastro de Pacientes
- Os pacientes também precisam de cadastro, contendo dados pessoais:
 - id
 - Nome
 - Data de nascimento
 - Genero
 - Uso_medicamento
 - Documentos -> (RG, Digito, CPF, cartao_sus, status_paciente, data_de_cadastro, ultima_alteracao)
 - Contatos -> (Email, Telefone)
 - Endereco -> (CEP, rua/avenida, numero/bloco, complemento, bairro, cidade, e estado).
 - Tipo_sanguineo
 - Convenio -> (nome, CNPJ, tempo_carencia e numero_carteira).
 - Alergias -> (alimento, observação e reação)

## CODE:
```kt
 "_id": "pac02",
    "nome": "Lucas Fernando Oliveira",
    "data_nascimento": "1995.05.15",
    "genero": "masculino",
    "uso_medicamento": false,

    "documento": {
      "RG": "98765432",
      "digito": "5",
      "CPF": 12345678901,
      "cartao_sus": 987654321234567,
      "status_paciente": "1",
      "data_de_cadastro": "2023.08.20",
      "ultima_alteracao": "2023.08.20"
    },
    "contato": {
      "contato_1": {
        "email": "lucasfer1995@gmail.com",
        "telefone": 11987654321,
        "whatsapp": true,
        "telefone_fixo": false
      },

      "contato_2": {
        "telefone": 1123456789,
        "whatsapp": false,
        "telefone_fixo": true
      }
    },

    "endereco": {
      "cep": "12345-678",
      "rua/avenida": "Avenida Brasil",
      "numero/bloco": "45",
      "complemento": "apto 12",
      "bairro": "Centro",
      "cidade": "Rio de Janeiro",
      "estado": "Rio de Janeiro"
    },
    "tipo_sanguineo": "O-",

    "convenio": {
      "nome": "Saúde Total",
      "cpnj": "98.765.432/0001-01",
      "tempo_carencia": "30 dias",
      "numero_carteira": "3456789/0003"
    },

    "alergias": {
      "alergia_1": {
        "alimento": "Amendoim",
        "observacao": "Reação severa. Necessita de atendimento imediato.",
        "reacao": "Inchaço, Dificuldade para respirar."
      },

      "alergia_2": {
        "remedio": "Ibuprofeno",
        "reação": "Erupção cutânea, Náusea."
      }
    }
  }
```

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
