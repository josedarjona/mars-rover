// Rover Object Goes Here
// ======================

var rover = {
  direction: "n",
  x : 0,
  y : 0,
  moveLog : [],

};



// ======================
function turnLeft(rover){
  
  console.log("turnLeft was called!");

  switch(rover.direction)
  {
      case "n" : rover.direction = "w"
      break;
      case "w" : rover.direction = "s"
      break;
      case "s" : rover.direction = "e"
      break;
      case "e" : rover.direction = "n"
      break;
      default : rover.direction 
    
  }

}

function turnRight(rover){

  console.log("turnRight was called!");
  switch(rover.direction)
  {
      case "n" : rover.direction = "e"
      break;
      case "e" : rover.direction = "s"
      break;
      case "s" : rover.direction = "w"
      break;
      case "w" : rover.direction = "n"
      break;
      default : rover.direction 
    
  }

  
}

function moveForward(rover){
  console.log("moveForward was called")
  switch(rover.direction)
  {
      case "n" : rover.y += 1
      break;
      case "w" : rover.x -= 1
      break;
      case "s" : rover.y -= 1
      break;
      case "e" : rover.x += 1
      break;
      default : rover.direction 
    
  }
  console.log("x: " + rover.x, "y:" + rover.y);
}

function commands(comm){
  for (i=0; i <= comm.length; i++){
    if (comm[i] === "f"){
      moveForward(rover);
    }else
    if (comm[i] === "r") {
      turnRight(rover);
    }else
    if (comm[i] === "l") {
      turnLeft(rover);
    }
    
  }
  rover.moveLog.push(["x: "+ rover.x, "y: " + rover.y])
  console.log(rover.moveLog)
}
