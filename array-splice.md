# Array Splice Method

* mutates the original array it's called on
* used for both removing and inserting elements
* Removal: 'splice(targetIndex, numToRemove)'
  - removes 'numToRemove' elements starting from 'targetIndex'
  - returns an array containing the removed elements
* Insertion: 'splice(targetIndex, numToRemove, ...elementsToInsert)'
  - inserts 'elementsToInsert' at 'targetIndex'
  - does not remove any elements ('numToRemove is 0)
* verstile: can remove, insert, or do both simultaeneously
