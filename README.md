****Semana 12 - Introdução ao Banco de Dados****

Aluna : Ana Claudia Almeida

Prof.: Vanessa Jansen

Rotas Usadas no MongoDB para manipulação das Informações

- Inserção de documentos;
- Atualização de documentos;
- Exclusão de documentos;
- Consulta com projeção;
- Consulta utilizando combinação entre os seletores;
- Consulta paginada e ordenada (utilizar skip, limit e sort)

***Inserção de documentos***

db.pets.insertMany([</br>
    {</br>
        "id": 1,</br>
        "nomeFantasia": "Pet Shop 1",</br>
        "endereco": "Avenida Paulista, 1273 - São Paulo",</br>
        "telefone": "11 12345-6789",</br>
        "atende": [</br>
            "cães",</br>
            "gatos"</br>
        ]</br>
    },</br>
])</br>

***Para consultar sua inclusão:***

db.getCollection('Localidades').find({})


***Atualização de documentos***

db.getCollection('Localidades').update(
    {
        "Pais" : "Mexico"
    },

    {
         $set: {
            "Visitas": "4"
        }
    },
    
    {
        "multi" : false, 
        
    }
);


***Exclusão de documentos***

Excluir paises com "4" visitas

db.getCollection('Localidades').remove({
    "Visitas": { $ne: "4" }
})
