# Objects-spaceship
This code follows the Objects lesson
How do I access the methods of each crew member? (See Line 34-61!)

let spaceship = {
  crew: {
    captain: { 
      name: 'Lily', 
      degree: 'Computer Engineering', 
      cheerTeam() { console.log('You got this!') } 
    },
    'chief officer': { 
      name: 'Dan', 
      degree: 'Aerospace Engineering', 
      agree() { console.log('I agree, captain!') } 
    },
    medic: { 
      name: 'Clementine', 
      degree: 'Physics', 
      announce() { console.log(`Jets on!`) } },
    translator: {
      name: 'Shauna', 
      degree: 'Conservation Science', 
      powerFuel() { console.log('The tank is full!') } 
    }
  }
}; 
 
// for...in
for (let crewMember in spaceship.crew) {
  console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`);
}

for (let crewMember in spaceship.crew) {
  //shorten spaceship.crew[crewMember] to ref for convenience
  const ref = spaceship.crew[crewMember];
  const name = ref.name;
  //function to determine which method to invoke
  const myFunction = memberName => {
    switch (memberName) {
      case 'Lily':
        return ref.cheerTeam();
      case 'Dan':
        return ref.agree();
      case 'Clementine':
        return ref.announce();
      case 'Shauna':
        return ref.powerFuel();
      default:
        return 'Hello World!';
    }
  }

  console.log(`${name}: ${myFunction(name)}`);
}
/*Output:
Lily: You got this!
Dan: I agree, captain!
Clementine: Jets on!
Shauna: The tank is full!
*/
