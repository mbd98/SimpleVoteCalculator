# Simple Election Calculator
This program can be used to determine the winner(s) of a Schulze-style or score-style election.

* [Usage](#usage)
* [Examples](#examples)
    + [Score/Approval](#score-approval)
    + [Schulze](#schulze)
* [References](#references)

## Usage
```
$ election -help
Takes a list of comma-separated values (CSV) from standard in.
The first line (header) is the list of candidates.
The following lines are ballots, where column entries correspond to the candidate's score from the ballot.
Flags:
  -schulze
        Use the Schulze method.  Lower ballot column entries yield a better rank for the corresponding candidate.
  -score
        Use the score method.  Higher ballot column entries yield a better score for the corresponding candidate.
```
## Examples
### Score/Approval
Here's a simple example for an approval-style election with 4 candidates: Adam, Beth, Charles, and Denise.

We will use the [`approval_test.csv`](./approval_test.csv) file as input.

Note that approval voting maps to score voting where approve = 1, neutral = 0, and reject = -1.

From this we determine that Beth is the winner, followed by Adam and Denise who are tied, then Charles.

### Schulze
We have 5 candidates: Adam, Beth, Charles, Denise, and Edward.

We will use the [`schulze_test.csv`](./schulze_test.csv) file as input.

From this we determine that Adam is the winner, followed by Beth and Charles who are tied, then Edward, then finally Denise.

## References
* Markus Schulze, *The Schulze Method of Voting*, https://arxiv.org/abs/1804.02973
* ElectoWiki et al., *Schulze method*, https://electowiki.org/wiki/Schulze_method
* Wikipedia et al., *Schulze method*, https://en.wikipedia.org/wiki/Schulze_method
