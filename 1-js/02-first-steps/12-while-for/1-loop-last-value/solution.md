উত্তর: `1`.

```js run
let i = 3;

while (i) {
  alert( i-- );
}
```

পর্রতিটি লুপের পুনরাবৃত্তি `i` এর মান `1` করে কমাচ্ছে। এখানে `while(i)` `i` এর মান পরীক্ষা করে এবং `i = 0`হলে লুপ থামিয়ে দেয়।

অতএব, লুপের প্রতিটি ধাপ পর্যায়ক্রমে লুপটিকে চূড়ান্ত অবস্থায় পৌছে দেয়:

```js
let i = 3;

alert(i--); // shows 3, decreases i to 2

alert(i--) // shows 2, decreases i to 1

alert(i--) // shows 1, decreases i to 0

// done, while(i) check stops the loop
```
