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
