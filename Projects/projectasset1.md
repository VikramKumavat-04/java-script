# PROJECT RELATED TO DOM

## PROJECT LINK
[CLICK HERE]( https://stackblitz.com/edit/dom-project-chaiaurcode?file=index.html)

# SOLUTION CODE 
## PROJECT 1
```javascript 
let body=document.querySelector('body');
let but=document.querySelectorAll('.button');
// console.log(but);
but.forEach((button)=>{
  button.addEventListener('click',(e)=>{
        console.log(e.target.id);
        if((e.target.id)=='blue'){
          body.style.backgroundColor=e.target.id
        }
        if((e.target.id)=='white'){
          body.style.backgroundColor=e.target.id
        }
        if((e.target.id)=='grey'){
          body.style.backgroundColor=e.target.id
        }
        if((e.target.id)=='yellow'){
          body.style.backgroundColor=e.target.id
        }


  })
 
})

```
# PROJECT 2 SOLUTION
```javascript
const form=document.querySelector('form');
form.addEventListener('submit',function(e){
  e.preventDefault();
const height=parseInt(document.querySelector('#height').value);
const weight=parseInt(document.querySelector('#weight').value);
const results=(document.querySelector('#results'));

if(height&&weight ===''|| height<0||isNaN(height&&weight)){
 results.innerHTML='Plese give a valid input ';
}
else{
let bmi=(weight/((height*height)/1000)).toFixed(2)
results.innerText=`${bmi}`;
}
})
```

# PROJECT 3 SOLLUTION
```javascript
const clock=document.querySelector('#clock');



setInterval(()=>{
  let date = new Date();
  clock.innerText=date.toLocaleTimeString();

},1000)
```
# PROJECT 4 SOLUTION

```javascript

const userInput=document.querySelector('#guessField');

const submit=document.querySelector('#subt');

const random=(Math.floor(Math.random()*100+1));

const guessSlot =document.querySelector('.guesses');

const remaining=document.querySelector('.lastResult');

const lowOrHigh=document.querySelector('.lowOrHi');

const startover=document.querySelector('.resultParas');

const p=document.createElement('p');

let prevGuess=[];
let numGuess=1;
let playGame= true
if(playGame)
{
  submit.addEventListener('click',(e)=>{
e.preventDefault();
const guess=parseInt(userInput.value);
validateGuess(guess);

  })
}

function validateGuess(guess){
  
if(isNaN(guess)){
  alert('plese enter valid input')
}
else if(guess<1){
alert("enter number more than 1")
}
else if(guess>100){
  alert("enter number less than 100")
  }
  prevGuess.push(guess)
  if(numGuess === ){
   displayGuess(guess);
   displayMessage(`Game Over Random NUmber Was ${guess}`)
   endGame();

  }
  else{
     displayGuess(guess)
     checkGuess(guess)

  }

}
function checkGuess(guess){
if(guess===random){
  displayMessage('You Guessed it Right!')
  endGame();

}
else if(guess<random){
  displayMessage('number is too Low')
}
else if(guess>random){
  displayMessage('number is too High')
}
}
function displayGuess(guess)
{
  userInput.value=''
  guessSlot.innerHTML+=`${ guess},`;
  numGuess++;
  remaining.innerHTML=`${11-numGuess}`
  
}
function displayMessage(message)
{
lowOrHigh.innerHTML=`<h2>${message}</h2>`

}

function newGame(){

  const newGame=document.querySelector('#newGame')
  newGame.addEventListener('click',(e)=>{
    random=Math.floor(Math.random()*100+1)
    prevGuess=[]
    newGuess=1
    guessSlot.innerHTML=''
    remaining.innerHTML=`${11-numGuess}`
    userInput.removeAttribute('disabled')
    startover.removeChild(p)
  })

}
function endGame(){
  userInput.value=''
  userInput.setAttribute('disabled','')
  p.classList.add('button')
  p.innerHTML=`<h2 id="newGame"> start new game </h2>`
  startover.appendChild(p)
  playGame=false
  newGame()

}
console.log(random);
```