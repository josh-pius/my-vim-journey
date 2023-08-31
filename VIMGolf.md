### General
- Gamify  VIM learning using VIM Golf.
- Challenges are games evaluated based on the number of characters you use to transform the starting file to get the desired result.


### Installation
1. Install python and PIP
2. `pip install vimgolf`


### Playing a Challenge
- You can go the site and find the id for a challenge, then run
```
python3 -m vimgolf put <challenge-id>
```


### Enumerate Bullets Challenge
1. Saw how powerful search and replace expressions combined with registers can be
2. Replace hyphened list with a numbered list `:let @a=1|%s/^-/\=(@a+setreg('a',@a+1).'.')/g<CR>`
3. Zero-pad numbers to be two digits always: `:%s/^\([0-9><BS>]\.\)/0\1/g<CR>`