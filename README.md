# MongoDB Aggregation Pipeline Bug: Incorrect $inc usage

This repository demonstrates a common error when using the `$inc` operator within the `$project` stage of a MongoDB aggregation pipeline. The `$inc` operator is designed to increment numeric fields, but applying it directly within `$project` as shown in `bug.js` will not produce the expected result.  The corrected implementation in `bugSolution.js` shows the proper approach.

## Problem
The original code attempts to increment the 'count' field.  However, `$inc` expects an existing field to increment. In the original code it is attempting to increment within the $project stage which does not work as intended.

## Solution
The solution shows how to properly increment the count field, either by using an intermediary variable, before the project stage, or directly within the $project stage using the $add operator.