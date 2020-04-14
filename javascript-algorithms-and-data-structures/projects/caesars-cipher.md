# freeCodeCamp JavaScript Algorithms and Data Structures Projects - Caesars Cipher

One of the simplest and most widely known _ciphers_ is a _Caesar cipher_, also known as a _shift cipher_. In a shift cipher the meanings of the letters are shifted by some set amount.

A common modern use is the [ROT13](https://en.wikipedia.org/wiki/ROT13) cipher, where the values of the letters are shifted by 13 places. Thus 'A' ↔ 'N', 'B' ↔ 'O' and so on.

Write a function which takes a [ROT13](https://en.wikipedia.org/wiki/ROT13) encoded string as input and returns a decoded string.

All letters will be uppercase. Do not transform any non-alphabetic character (i.e. spaces, punctuation), but do pass them on.

## Tests

```javascript
* rot13("SERR PBQR PNZC") // should decode to "FREE CODE CAMP"
* rot13("SERR CVMMN!") // should decode to "FREE PIZZA!"
* rot13("SERR YBIR?") // should decode to "FREE LOVE?"
* rot13("GUR DHVPX OEBJA SBK WHZCF BIRE GUR YNML QBT.") // should decode to "THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG."
```

## My Solution

```javascript
function rot13(str) {
  const regex = /[A-Z]/;
  let newStr = "";

  for (let i = 0; i < str.length; i++) {
    if (regex.test(str[i])) {
      let char = str.charCodeAt(i);

      if (char + 13 > 90) {
        char -= 26;
      }

      newStr += String.fromCharCode(char + 13);
    } else {
      newStr += str[i];
    }
  }

  return newStr;
}
```

| [Portfolio Website](http://arnoldgelacio.com) | [freeCodeCamp Profile](https://freecodecamp.org/arnoldgelacio) |
