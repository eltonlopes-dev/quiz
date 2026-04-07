const questionElement = document.getElementById('question');
const answerButtonsElement = document.getElementById('answer-buttons');
const nextButton = document.getElementById('next-btn');
const acertosElement = document.getElementById('correct-score');
const errosElement = document.getElementById('wrong-score');

// Elementos da Modal
const resultModal = document.getElementById('result-modal');
const resultMessage = document.getElementById('result-message');
const resultStats = document.getElementById('result-stats');

let currentQuestionIndex = 0;
let acertos = 0;
let erros = 0;

// (Aqui ficam as 20 perguntas que enviei na resposta anterior)
const questions = [
    { question: 'Segundo a Bíblia, quem construiu a arca para sobreviver ao Dilúvio?', answers: [{ text: 'Moisés', correct: false }, { text: 'Noé', correct: true }, { text: 'Abraão', correct: false }, { text: 'Davi', correct: false }] },
    { question: 'Qual é o primeiro livro da Bíblia?', answers: [{ text: 'Êxodo', correct: false }, { text: 'Salmos', correct: false }, { text: 'Apocalipse', correct: false }, { text: 'Gênesis', correct: true }] },
    { question: 'Quem derrotou o gigante Golias com apenas uma funda e uma pedra?', answers: [{ text: 'Saul', correct: false }, { text: 'Salomão', correct: false }, { text: 'Davi', correct: true }, { text: 'Sansão', correct: false }] },
    { question: 'Quantos discípulos Jesus escolheu inicialmente?', answers: [{ text: '7', correct: false }, { text: '10', correct: false }, { text: '12', correct: true }, { text: '40', correct: false }] },
    { question: 'Onde Jesus nasceu?', answers: [{ text: 'Jerusalém', correct: false }, { text: 'Nazaré', correct: false }, { text: 'Belém', correct: true }, { text: 'Roma', correct: false }] },
    { question: 'Qual mar Moisés abriu, com a ajuda de Deus, para os hebreus passarem?', answers: [{ text: 'Mar Morto', correct: false }, { text: 'Mar Vermelho', correct: true }, { text: 'Mar da Galiléia', correct: false }, { text: 'Mar Mediterrâneo', correct: false }] },
    { question: 'Quem foi traído por 30 moedas de prata?', answers: [{ text: 'Pedro', correct: false }, { text: 'João Batista', correct: false }, { text: 'Paulo', correct: false }, { text: 'Jesus', correct: true }] },
    { question: 'Qual desses homens sobreviveu a uma cova de leões?', answers: [{ text: 'Daniel', correct: true }, { text: 'Elias', correct: false }, { text: 'Jeremias', correct: false }, { text: 'José', correct: false }] },
    { question: 'Segundo o Antigo Testamento, quem recebeu os Dez Mandamentos no Monte Sinai?', answers: [{ text: 'Izaque', correct: false }, { text: 'Moisés', correct: true }, { text: 'Arão', correct: false }, { text: 'Josué', correct: false }] },
    { question: 'Qual é o "Mandamento Resumido" que Jesus ensinou como o maior de todos?', answers: [{ text: 'Não matarás', correct: false }, { text: 'Amarás o teu próximo como a ti mesmo e a Deus sobre todas as coisas', correct: true }, { text: 'Guardarás o sábado', correct: false }, { text: 'Honrarás pai e mãe', correct: false }] },
    { question: 'Quem foi a esposa de Abraão e mãe de Izaque?', answers: [{ text: 'Rebeca', correct: false }, { text: 'Lia', correct: false }, { text: 'Sara', correct: true }, { text: 'Raquel', correct: false }] },
    { question: 'Qual foi o discípulo que negou Jesus três vezes antes do galo cantar?', answers: [{ text: 'Judas Iscariotes', correct: false }, { text: 'Pedro', correct: true }, { text: 'André', correct: false }, { text: 'Tomé', correct: false }] },
    { question: 'Quem escreveu a maioria das epístolas (cartas) no Novo Testamento?', answers: [{ text: 'João', correct: false }, { text: 'Pedro', correct: false }, { text: 'Paulo', correct: true }, { text: 'Lucas', correct: false }] },
    { question: 'Qual homem bíblico era conhecido por sua força extraordinária, ligada ao seu cabelo?', answers: [{ text: 'Sansão', correct: true }, { text: 'Gideão', correct: false }, { text: 'Saul', correct: false }, { text: 'Absalão', correct: false }] },
    { question: 'Quem foi vendido como escravo por seus próprios irmãos e depois tornou-se governador do Egito?', answers: [{ text: 'Benjamim', correct: false }, { text: 'José', correct: true }, { text: 'Rúben', correct: false }, { text: 'Levi', correct: false }] },
    { question: 'Qual profeta foi engolido por um grande peixe após tentar fugir da ordem de Deus?', answers: [{ text: 'Ezequiel', correct: false }, { text: 'Miquéias', correct: false }, { text: 'Oseias', correct: false }, { text: 'Jonas', correct: true }] },
    { question: 'No Sermão da Montanha, Jesus ensina sobre as:', answers: [{ text: 'Parábolas do Reino', correct: false }, { text: 'Bem-aventuranças', correct: true }, { text: 'Dez Pragas do Egito', correct: false }, { text: 'Profecias do Fim', correct: false }] },
    { question: 'Quem foi o rei conhecido por sua imensa sabedoria e por construir o primeiro Templo em Jerusalém?', answers: [{ text: 'Salomão', correct: true }, { text: 'Davi', correct: false }, { text: 'Ezequias', correct: false }, { text: 'Josias', correct: false }] },
    { question: 'Quem foi lançado na fornalha ardente, mas não se queimou?', answers: [{ text: 'Sadraque, Mesaque e Abede-Nego', correct: true }, { text: 'Daniel e seus amigos', correct: false }, { text: 'Elias e Eliseu', correct: false }, { text: 'Moisés e Arão', correct: false }] },
    { question: 'Qual é o último livro da Bíblia?', answers: [{ text: 'Apocalipse', correct: true }, { text: 'Judas', correct: false }, { text: 'Malaquias', correct: false }, { text: 'Hebreus', correct: false }] }
];

function startQuiz() {
    currentQuestionIndex = 0;
    acertos = 0;
    erros = 0;
    acertosElement.innerText = '0';
    errosElement.innerText = '0';
    nextButton.classList.add('hide');
    resultModal.classList.add('hide'); // Esconde a modal ao reiniciar
    showQuestion();
}

function showQuestion() {
    resetState();
    let currentQuestion = questions[currentQuestionIndex];
    questionElement.innerText = `${currentQuestionIndex + 1}. ${currentQuestion.question}`;

    currentQuestion.answers.forEach(answer => {
        const button = document.createElement('button');
        button.innerText = answer.text;
        button.classList.add('btn');
        button.addEventListener('click', () => selectAnswer(answer, button));
        answerButtonsElement.appendChild(button);
    });
}

function resetState() {
    nextButton.classList.add('hide');
    while (answerButtonsElement.firstChild) {
        answerButtonsElement.removeChild(answerButtonsElement.firstChild);
    }
}

function selectAnswer(answer, selectedButton) {
    const isCorrect = answer.correct;
    if (isCorrect) {
        selectedButton.classList.add('correct');
        acertos++;
        acertosElement.innerText = acertos;
    } else {
        selectedButton.classList.add('wrong');
        erros++;
        errosElement.innerText = erros;
        Array.from(answerButtonsElement.children).forEach(button => {
            const findAnswer = questions[currentQuestionIndex].answers.find(a => a.text === button.innerText);
            if (findAnswer.correct) button.classList.add('correct');
        });
    }

    Array.from(answerButtonsElement.children).forEach(button => button.disabled = true);

    if (questions.length > currentQuestionIndex + 1) {
        nextButton.innerText = 'Próxima Pergunta';
        nextButton.classList.remove('hide');
    } else {
        showFinalResult(); // Chama o resultado final
    }
}

function showFinalResult() {
    resultModal.classList.remove('hide');
    resultStats.innerText = `Acertos: ${acertos} | Erros: ${erros}`;

    if (acertos === 20) {
        resultMessage.innerText = "Parabéns!";
    } else if (acertos >= 15) {
        resultMessage.innerText = "Boa!";
    } else if (acertos >= 10) {
        resultMessage.innerText = "Resultado:";
    } else {
        resultMessage.innerText = "Você precisa estudar mais";
    }
}

nextButton.addEventListener('click', () => {
    currentQuestionIndex++;
    showQuestion();
});

startQuiz();
