# algoExpert-Medium-Exercises

/*Three Number Sum - Given a target sum, return all possible triplets which add up to the target sum. Be sure that all triplets are sorted.*/

type Triplet = [number, number, number];

export function threeNumberSum(array: number[], targetSum: number): Triplet[] {
  let combos: Triplet[] = []
  const sorted_array: number[] = array.sort((a,b) => a - b );
  for (let i = 0; i < array.length - 2; i ++){
    for (let j = i + 1; j < array.length - 1; j ++){
      for (let k = j + 1; k < array.length; k ++){
        let nums: Triplet = [array[i], array[j], array[k]];
        if ((array[i]+array[j]+array[k]) === targetSum){
          combos.push(nums);
        } else {
          continue;
        }
      }
    }
  }
  return combos;
}


/*zerosumSubarray - Given an array, check if it contains a subarray that sums up to zero*/
export function zeroSumSubarray(nums: number[]) {

  if (nums.length == 1){
    if (nums[0] === 0){
      return true;
    } else {
      return false;
    }


  }
  let sum = 0;
  let sums: number[] = []
  for (let i = 0; i < nums.length; i ++){
      sum += nums[i];
      sums.push(sum);
  }

  for (let i = 0; i < sums.length - 1; i++){
      for (let j = i + 1; j < sums.length ; j ++){
          if (sums[i] === sums[j] || sums[i] === 0 || sums[j] === 0){
              return true;
          } else {
              continue;
          }
      }
  }
  return false;
}
