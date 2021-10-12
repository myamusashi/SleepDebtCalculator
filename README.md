# SleepDebtCalculator
Sleep Debt Calculator Project
const getSleepHours = day => {

 if (day === 'monday') {
   return 7;
 } else if (day === 'thursday') {
   return 6;
 } else if (day === 'wednesday') {
   return 6;
 } else if (day === 'tuesday') {
   return 8;
 } else if (day === 'friday') {
   return 5;
 } else if (day === 'saturday') {
   return 6;
 } else if (day === 'sunday') {
 }
};

const getActualSleepHours = () => getSleepHours('monday') + getSleepHours('tuesday') + getSleepHours('wednesday') + getSleepHours('thursday') + getSleepHours('friday') + getSleepHours('saturday') + getSleepHours('sunday');

const getIdealSleepHours = (idealHours) => idealHours * 7;

const calculateSleepDebt = (idealHours) => {
  const actualSleepHours = getActualSleepHours();
  const idealSleepHours = getIdealSleepHours(idealHours);

  if (actualSleepHours === idealSleepHours) {
    console.log('You got the perfect amount of sleep. Good job!');
  } else if (actualSleepHours >= idealSleepHours) {
    console.log(`You got ${actualSleepHours - idealSleepHours} hour(s) more sleep than you needed this week.`);
  } else {
    console.log(`You got ${idealSleepHours - actualSleepHours} hour(s) less sleep than you needed this week. Get some rest.`);
  }
}

calculateSleepDebt(8.5);
