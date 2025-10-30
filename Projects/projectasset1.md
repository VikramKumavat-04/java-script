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
#PROJECT 2
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