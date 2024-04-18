```
(function (){
    let pickAnswer = (element, data) => {
        Array.from(element.querySelectorAll(`input[value="${data.answer}"]`)).forEach(
            (v,i)=>{
                v.click();
            }
        )
    }
    let getQuestion = (data) => {
        QAinHTML.forEach((item) => {
            if (item.innerText.toLowerCase().includes(data.question.toLowerCase())) {
                pickAnswer(item, data);
                return true;
            }
        });
    };
    data=[ {
        "question":"",
        "item":""
    }]
    for(const item of data){
        getQuestion(item)
    }
    QAinHTML[QAinHTML.length - 1].scrollIntoView();
})()
```
