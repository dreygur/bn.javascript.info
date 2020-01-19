এই টাস্কটায় প্রিফিক্স/পোস্টফিক্স ফর্ম তুলনা করার সময় কিভাবে আলাদা ফলাফল দিতে পারে সেটা দেখানো হবে।

1. **১ থেকে ৪ পর্যন্ত**

    ```js run
    let i = 0;
    while (++i < 5) alert( i );
    ```

    প্রথম মান `i = 1`, কারণ `++i`  `i` -কে বাড়িয়ে নতুন মান দেয়।. সুতরাং প্রথম তুলনা `1 < 5` এবং `alert` এ মান `1`.

    তারপর ক্রমান্বয়ে `2, 3, 4…` -- মানগুলো একের পর এক আসতে থাকে. তুলনার সময় প্রতিবার বাড়তি মানটা নেয়া হয়, কারণ ভ্যারিয়েবলের আগে `++` আছে।

    সবশেষে, `i = 4` বেরে `5` হয়েছে, `while(5 < 5)` -এই তুলনাটা অচল হয়ে যায় আর লুপটাও থেমে যায়. তাই `5` দেখা যায় না।
2. **১ থেকে ৫ পর্যন্ত**

    ```js run
    let i = 0;
    while (i++ < 5) alert( i );
    ```

    আবারও প্রথম মান `i = 1`. `i++` -এর পোস্টফিক্স ফর্ম `i` এর মান বাড়ায় এবং আগের মান রিটার্ন করে, সুতরাং `i++ < 5` তুলনায়  `i = 0` (`++i < 5` -এর বিপরীত).

    কিন্তু `alert` কলটা আলাদা. It's another statement which executes after the increment and the comparison. So it gets the current `i = 1`.

    Then follow `2, 3, 4…`

    Let's stop on `i = 4`. The prefix form `++i` would increment it and use `5` in the comparison. But here we have the postfix form `i++`. So it increments `i` to `5`, but returns the old value. Hence the comparison is actually `while(4 < 5)` -- true, and the control goes on to `alert`.

    The value `i = 5` is the last one, because on the next step `while(5 < 5)` is false.
