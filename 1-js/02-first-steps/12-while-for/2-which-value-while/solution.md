এই টাস্কটায় প্রিফিক্স/পোস্টফিক্স ফর্ম তুলনা করার সময় কিভাবে আলাদা ফলাফল দিতে পারে সেটা দেখানো হবে।

1. **১ থেকে ৪ পর্যন্ত**

    ```js run
    let i = 0;
    while (++i < 5) alert( i );
    ```

    প্রথম মান `i = 1`, কারণ `++i`  `i` -কে বাড়িয়ে নতুন মান দেয়।. সুতরাং প্রথম তুলনা `1 < 5` এবং `alert` এ মান `1`.

    তারপর ক্রমান্বয়ে `2, 3, 4…` -- মানগুলো একের পর এক আসতে থাকে. তুলনার সময় প্রতিবার বাড়তি মানটা নেয়া হয়, কারণ ভ্যারিয়েবলের আগে `++` আছে।

    সবশেষে, `i = 4` বেড়ে `5` হয়েছে, `while(5 < 5)` -এই তুলনাটা অচল হয়ে যায় আর লুপটাও থেমে যায়. তাই `5` দেখা যায় না।
2. **১ থেকে ৫ পর্যন্ত**

    ```js run
    let i = 0;
    while (i++ < 5) alert( i );
    ```

    আবারও প্রথম মান `i = 1`. `i++` -এর পোস্টফিক্স ফর্ম `i` এর মান বাড়ায় এবং আগের মান রিটার্ন করে, সুতরাং `i++ < 5` তুলনায়  `i = 0` (`++i < 5` -এর বিপরীত).

    কিন্তু `alert` কলটা আলাদা. এটা একটা আলাদা স্টেটমেন্ট যা প্রতিবার ইনক্রিমেন্ট এবং তুলনা শেষে এক্সিকিউট হয়। ফলে এর মান দাঁড়ায় `i = 1`
    
    আর তারপর `2, 3, 4...`
    
    এবার `i = 4` এ থামা যাক। `++1` ফ্রিফিক্স ফর্মটা এর মান বাড়িয়ে একে `5` করে তারপর তুলনা করবে। কিন্তু আমাদের কাছে আছে `i++` য়া পোস্টফিক্স ফর্ম। তাই এটি `i` কে বাড়িয়ে `5` করে, কিন্তু পুরোো মানটাই রিটার্ন করবে। ফলে তুলনাটা আসলে `while(4 < 5)` -- true, আর কট্রোলটা `alert` এর কাছে চলে যায়।


    `i = 5` মানটাই শেষ মান, কারণ পরের ধাপে `while(5 < 5)` false
