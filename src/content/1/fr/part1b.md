
const Header =(props) => {
  return (
 
    <h>
      {props.course} 
    </h>)
}

const CourseItem = (props) => {
  const x = 10
  let y = 5
  //console.log(x,y)
    return (
     
      <p>
        {props.description} {props.nbexercice}
      </p>
     
    )
}
const Total = (props) => {
  return (
  <label>Le cours est constitué de : {props.parts[0].exercises 
                                      + props.parts[1].exercises 
                                      + props.parts[2].exercises} exercices</label>
  )
}




const App = () => {

    const Content =(props) => {
      return (
        <>
        <CourseItem description ={props.parts[0].name} nbexercice = {props.parts[0].exercices} />
        <CourseItem description ={props.parts[1].name} nbexercice = {props.parts[1].exercices} />
        <CourseItem description ={props.parts[2].name} nbexercice = {props.parts[2].exercices} />
        </>
        )
       
    }
    const course = {
      name: 'Half Stack application development',
      parts: [
        {
          name: 'Fundamentals of React',
          exercises: 10
        },
        {
          name: 'Using props to pass data',
          exercises: 7
        },
        {
          name: 'State of a component',
          exercises: 14
        }
      ]
    }

    const arto = {
      name: 'Arto Hellas',
      age: 35,
      education: 'PhD',
      greet: function() {
        console.log('hello, my name is ' + this.name)
      },
      doAddition: function(a, b) {
        console.log(a + b)
      },
    }
 
    /*
    arto.greet()  // "hello, my name is Arto Hellas" est affiché
    arto.growOlder = function() {
      this.age += 1
    }
    arto.growOlder()
    console.log(arto.age)   // 36 est affiché 
    
    arto.doAddition(1, 4)        // 5 est affiché
    const referenceToAddition = arto.doAddition
    referenceToAddition(10, 15) 
    
    arto.greet()
    const referenceToGreet = arto.greet
    referenceToGreet() 

    setTimeout(arto.greet, 1000)
        */

    setTimeout(arto.greet.bind(arto), 1000)
    
    return (
      <>
        <Header course={course.name} />
        <Content parts ={course.parts}/>
        <Total parts={course.parts} />
      </>
    )
  }
  
  export default App
