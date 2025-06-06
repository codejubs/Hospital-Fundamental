## 🏥 Hospital Fundamental - Sistema de Gerenciamento Clínico

## Descrição do Projeto

Um hospital local precisa desenvolver um sistema para gerenciar seus dados clínicos e substituir planilhas e arquivos antigos por um banco de dados funcional. O objetivo é criar uma estrutura que registre médicos, pacientes, consultas, convênios, receitas médicas e muito mais.

## Requisitos do Sistema

### 👨‍⚕️ Cadastro de Médicos
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

### 🤕 Cadastro de Pacientes
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

## Code:
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

### 🩺💊 Registro de Consultas
- As consultas também têm sido registradas em planilhas, com as seguintes informações:
 - id
 - CRM_medico
 - id_paciente
 - Valor
 - Conveniada (sim/não)
 - Especialidade_buscada
 - Descricao
 - Data_hora
 - Receita -> Medicamentos ->  (nome, quantidade e instruções).
 - Convenio -> (nome, CNPJ, tempo_carencia e numero_carteira).

## Code:
```kt
"_id": "consul18",
      "CRM_medico": "RJ986342",
      "id_paciente": "pac10",
      "valor": "240,00",
      "conveniada": false,
      "especialidade_buscada": "Psiquiatria",
      "descricao": "Consulta para avaliação de ansiedade e prescrição de medicamentos.",
      "data_hora": "2022-08-10 13:00",
      "receita": {
        "medicamentos": [
          {
            "nome": "Sertralina",
            "quantidade": "50mg",
            "instrucoes": "Tomar 1 comprimido ao dia"
          },
          {
            "nome": "Clonazepam",
            "quantidade": "0,5mg",
            "instrucoes": "Tomar 1 comprimido à noite"
          }
        ]
      },
      "convenio": {
        "nome": "Saúde Acessível",
        "cpnj": "01.234.567/0001-90",
        "tempo_carencia": "30 dias",
        "numero_carteira": "5678901/0006"
      }
    }
```

### 🛌💉 Registro de Internações
 As internações são vinculadas aos pacientes, médicos e quartos do hospital.

 ## Code:
 ```kt
"_id": "inter06",
    "id_paciente": "pac14",
    "CRM_medico": "RJ986342",
    "data_de_entrada": "2017.04.08 08:00:02",
    "data_prevista_alta": "2017.04.08 17:00:32",
    "data_efetiva_alta": "2017.04.09 09:00:04",
    "procedimentos": [
      "Terapia Comportamental"
    ],
    "quarto": "apto 33",
    "valor_diaria": "R$200,00 ",
    "COREN_enfermeiros": [
      "CRE74832",
      "CRE85275",
      "CRE96385"
    ]
  }
```

## MAPA MENTAL
![mapa mental](https://github.com/user-attachments/assets/146f62cc-73fa-4cfa-b9a7-9ea9aa45d385)

## Crie um script e nele inclua consultas que retornem:

* Todos os dados e o valor médio das consultas do ano de 2020 e das que foram feitas sob convênio.

   R: Valor médio das consultas sem conveniadas é R$ 200,00.
  
Code:
```js
db.consultas.aggregate([
  {
    $addFields: {
      dataConvertida: { $toDate: "$data_hora" }
    }
  },
  {
    $match: {
      dataConvertida: {
        $gte: ISODate("2020-01-01T00:00:00Z"),
        $lt: ISODate("2021-01-01T00:00:00Z")
      }
    }
  },
  {
    $group: {
      _id: {
        temConvenio: {
          $cond: [
            { $and: [{ $ne: ["$convenio", null] }, { $ne: ["$convenio", false] }] },
            "Com Convênio",
            "Sem Convênio"
          ]
        }
      },
      valorMedio: { $avg: "$valor" },
      totalConsultas: { $sum: 1 }
    }
  }
])
`````

* Todos os dados das internações que tiveram data de alta maior que a data prevista para a alta.
  
  Code:
```js
db.internacoes.find({
  $expr: { $gt: ["$data_efetiva_alta", "$data_prevista_alta"] }
});
````

* Receituário completo da primeira consulta registrada com receituário associado.

R:
```js
_id: 'consul01',
  CRM_medico: 'SC45938',
  id_paciente: 'pac02',
  valor: 190,
  conveniada: true,
  especialidade_buscada: 'Clínico Geral',
  descricao: 'Consulta para avaliação de dor de cabeça e prescrição de analgésicos.',
  data_hora: '2015-03-15T14:30:00Z',
  receita: {
    medicamentos: [
      {
        nome: 'Paracetamol',
        quantidade: '500mg',
        instrucoes: 'Tomar 1 comprimido a cada 8 horas'
      },
      {
        nome: 'Amoxicilina',
        quantidade: '250mg',
        instrucoes: 'Tomar 1 cápsula a cada 12 horas'
      }
    ]
  },
  convenio: {
    nome: 'Saúde Total',
    cpnj: '98.765.432/0001-01',
    tempo_carencia: '30 dias',
    numero_carteira: '3456789/0003'
  }
}
```
  
Code:
```js
db.consultas.find({
receita: {$exists: true}
}).sort({data_hora: 1}).limit(1)
````
*Todos os dados da consulta de maior valor e também da de menor valor (ambas as consultas não foram realizadas sob convênio).

R: O Maior valor é de R$ 260,00. A Menor é de R$ 180,00.

 Code: (Maior) e (Menor)
```js
db.consultas.find({
 conveniada: false
}).sort({valor: -1}).limit(1)

db.consultas.find({
 conveniada: false
}).sort({valor: 1}).limit(1)
```
* Todos os dados das internações em seus respectivos quartos, calculando o total da internação a partir do valor de diária do quarto e o número de dias entre a entrada e a alta.

 Code:
```js
db.internacoes.aggregate([
  {
    $addFields: {
      data_entrada_convertida: {
        $dateFromString: {
          dateString: "$data_de_entrada",
          format: "%Y.%m.%d %H:%M:%S"
        }
      },
      data_alta_convertida: {
        $dateFromString: {
          dateString: "$data_efetiva_alta",
          format: "%Y.%m.%d %H:%M:%S"
        }
      }
    }
  },
  {
    $addFields: {
      diasInternacao: {
        $dateDiff: {
          startDate: "$data_entrada_convertida",
          endDate: "$data_alta_convertida",
          unit: "day"
        }
      }
    }
  },
  {
    $lookup: {
      from: "quartos",
      localField: "id_quarto",
      foreignField: "id_quarto",
      as: "detalhes_quarto"
    }
  },
  { $unwind: "$detalhes_quarto" },
  {
    $addFields: {
      total_internacao: {
        $multiply: ["$detalhes_quarto.valor_diaria", "$diasInternacao"]
      }
    }
  },
  {
    $project: {
      _id: 1,
      id_paciente: 1,
      id_quarto: 1,
      diasInternacao: 1,
      total_internacao: 1,
      "detalhes_quarto.tipo_quarto": 1,
      "detalhes_quarto.valor_diaria": 1
    }
  }
])
````
* Data, procedimento e número de quarto de internações em quartos do tipo “apartamento”.
  
 R: 
```js
{
  _id: 'inter01',
  id_paciente: 'pac14',
  CRM_medico: 'RJ986342',
  data_de_entrada: '2016.04.02 14:00:59',
  data_prevista_alta: '2016.04.05 10:56:50',
  data_efetiva_alta: '2016.04.06 09:30:01',
  procedimentos: [
    'Exame de Sangue',
    'Observação Psiquiátrica'
  ],
  id_quarto: 'quar03',
  COREN_enfermeiros: [
    'CRE74832',
    'CRE85241'
  ]
},
{
  _id: 'inter06',
  id_paciente: 'pac14',
  CRM_medico: 'RJ986342',
  data_de_entrada: '2017.04.08 08:00:02',
  data_prevista_alta: '2017.04.08 17:00:32',
  data_efetiva_alta: '2017.04.09 09:00:04',
  procedimentos: [
    'Terapia Comportamental'
  ],
  id_quarto: 'quar03',
  COREN_enfermeiros: [
    'CRE74832',
    'CRE85275',
    'CRE96385'
  ]
},
{
  _id: 'inter07',
  id_paciente: 'pac05',
  CRM_medico: 'SP523469',
  data_de_entrada: '2022.02.08 03:27:02',
  data_prevista_alta: '2022.02.25 12:55:20',
  data_efetiva_alta: '2022.02.25 22:50:55',
  procedimentos: [
    'Cirurgia Herniorrafia'
  ],
  id_quarto: 'quar03',
  COREN_enfermeiros: [
    'CRE14789',
    'CRE14785'
  ]
},
{
  _id: 'inter07',
  id_paciente: 'pac05',
  CRM_medico: 'SP523469',
  data_de_entrada: '2022.02.08 03:27:02',
  data_prevista_alta: '2022.02.25 12:55:20',
  data_efetiva_alta: '2022.02.25 22:50:55',
  procedimentos: [
    'Cirurgia Herniorrafia'
  ],
  id_quarto: 'quar03',
  COREN_enfermeiros: [
    'CRE14789',
    'CRE14785'
  ]
}
````

 #Code: 
```js
db.internacoes.find({
 id_quarto: "quar03"
});
`````
* Nome do paciente, data da consulta e especialidade de todas as consultas em que os pacientes eram menores de 18 anos na data da consulta e cuja especialidade não seja “pediatria”, ordenando por data de realização da consulta.

#Code:
````js
{
db.consultas.aggregate([
  {
    $addFields: {
      idade_no_dia: {
        $dateDiff: {
          startDate: { $dateFromString: { dateString: "$data_de_nascimento" } },
          endDate: { $dateFromString: { dateString: "$data_consulta" } },
          unit: "year"
        }
      }
    }
  },
  {
    $match: {
      idade_no_dia: { $lt: 18 }, 
      especialidade: { $ne: "pediatria" } 
    }
  },
  {
    $sort: { data_consulta: 1 } 
  },
  {
    $project: {
      _id: 0,
      nome_paciente: 1,
      data_consulta: 1,
      especialidade: 1
    }
  }
])
}
````
*Nome do paciente, nome do médico, data da internação e procedimentos das internações realizadas por médicos da especialidade “gastroenterologia”, que tenham acontecido em “enfermaria”.

#Code:
````js
{
db.internacoes.aggregate([
  { $lookup: { from: "medicos", localField: "medico_responsavel", foreignField: "documentos.crm", as: "detalhes_medico" } },
  { $unwind: "$detalhes_medico" },
  { $match: { "detalhes_medico.especialidade": "gastroenterologia", tipo_de_quarto: "enfermaria" } },
  { $project: { nome_paciente: 1, nome_medico: "$detalhes_medico.nome", data_internacao: "$data_entrada", procedimentos: 1 } }
])
}
````
*Os nomes dos médicos, seus CRMs e a quantidade de consultas que cada um realizou.

#Code:
````js
{
db.consultas.aggregate([
  {
    $group: {
      _id: "$crm", // Agrupando por CRM do médico responsável
      numero_consultas: { $sum: 1 } 
    }
  },
  {
    $lookup: {
      from: "medicos", // Nome da coleção de médicos
      localField: "_id", // Campo agrupado (CRM)
      foreignField: "documentos.crm", 
      as: "detalhes_medico"
    }
  },
  { 
    $unwind: { path: "$detalhes_medico", preserveNullAndEmptyArrays: true } 
  },
  {
    $project: {
      _id: 0, // Remove o ID do agrupamento
      nome_medico: "$detalhes_medico.nome", 
      crm: "$_id", // CRM do médico
      numero_consultas: 1 
    }
  }
])
}
````
*Todos os médicos que tenham "Gabriel" no nome. 

R:
````js
{
  _id: 'doc4',
  nome: 'Gabriel Kotlin da Silva',
  data_nascimento: '1999.02.28',
  genero: 'masculino',
  especialidade: 'Cardiologista',
  tipo: 'Generalista',
  'endereço': {
    'rua/avenida': 'Av. 23 de Maio',
    'numero/bloco': '1010',
    complemento: 'Casa',
    bairro: 'Centro',
    cidade: 'São Paulo',
    estado: 'São Paulo',
    cep: '01311-000'
  },
  contato: {
    telefone: 11526482359,
    whatsapp: true,
    email: 'gabrielkotlin@hospitalmilu.com',
    email_pessoal: 'gabrielkotlindoc@gmail.com - não mandar emails sobre trabalho!'
  },
  status: 'não está em atividade no momento',
  'observação': 'não está recebendo pacientes',
  em_atividade: false,
  documentos: {
    CPF: 53462896415,
    CRM: 'RJ56324',
    RG: '18934985',
    digito: '7'
  },
  agenda: {
    'segunda-feira': 'Plantão',
    'terca-feira': 'Folga',
    'quarta-feira': 'Entre 9h à 19h',
    'quinta-feira': 'Plantão',
    'sexta-feira': 'Entre 6h à 12h',
    sabado: 'Entre 8h à 17h',
    domingo: 'Plantão',
    feriados: 'Folga'
  },
  plantao: {
    dia: 'segunda-feira',
    inicio: '20:00',
    fim: '14:00'
  },
  plantao_2: {
    dia: 'domingo',
    inicio: '20:00',
    fim: '14:00'
  }
}
````

#Code: 
````
{
db.medicos.find({
nome: /Gabriel/
})
}
````
*Os nomes, CORENs e número de internações de enfermeiros que participaram de mais de uma internação.

#Code:
`````js
{
db.internacoes.aggregate([
  { $unwind: "$enfermeiras_responsaveis" },
  {
    $group: {
      _id: "$enfermeiras_responsaveis",
      totalInternacoes: { $sum: 1 }
    }
  },
  { $match: { totalInternacoes: { $gt: 1 } } },
  {
    $lookup: {
      from: "enfermeiros",
      localField: "_id",
      foreignField: "coren",
      as: "detalhesEnfermeiro"
    }
  },
  {
    $project: {
      coren: "$_id",
      nome: { $arrayElemAt: ["$detalhesEnfermeiro.nome", 0] },
      totalInternacoes: 1
    }
  }
])
}
``````

