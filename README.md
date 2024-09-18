# aluno
let aluno = 
    {
        "nome": "Alyssa",
        "idade":  19,
        "curso": "Ciência da Computação",
        "notas": [7.0, 8.0, 9.0]
    };

console.log("nome: ", aluno.nome);
console.log("nota: ", aluno.notas[0]);

aluno.notas.push(10.0);
aluno.idade = 22;
console.log(aluno.notas);
console.log(aluno.idade);

let alunoString = JSON.stringify(aluno);
console.log(alunoString);      

let alunoParse = JSON.parse(alunoString);
console.log(alunoParse);          

for (let chave in aluno ){
    console.log(chave + ': ' + aluno[chave]);
}

let totalNotas = aluno.notas.reduce((acumulador, nota) => acumulador + nota, 0);
let mediaNotas = totalNotas / aluno.notas.length;
console.log(mediaNotas); 

aluno.endereco = {
    rua: "Rua das Flores",
    cidade: "São Paulo",
    estado: "SP"
};
console.log(aluno.endereco.cidade); 
console.log(aluno.endereco.estado); 

let alunos = [
    {
        nome: "João Silva",
        idade: 22,
        curso: "Engenharia",
        notas: [7.5, 8.0, 9.0, 8.5],
        endereco: {
            rua: "Rua das Flores",
            cidade: "São Paulo",
            estado: "SP"
        }
    },
    {
        nome: "Maria Oliveira",
        idade: 20,
        curso: "Medicina",
        notas: [9.0, 9.5, 8.5, 10.0],
        endereco: {
            rua: "Avenida Central",
            cidade: "Rio de Janeiro",
            estado: "RJ"
        }
    }
];
let alunosComMediaAlta = alunos.filter(aluno => {
    let totalNotas = aluno.notas.reduce((acumulador, nota) => acumulador + nota, 0);
    let mediaNotas = totalNotas / aluno.notas.length;
    return mediaNotas > 8;
});
console.log(alunosComMediaAlta); 
