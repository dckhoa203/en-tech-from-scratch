# Valid Anagram

> Mục tiêu hôm nay: nói rõ cách giải tối ưu bằng 8 câu tiếng Anh đơn giản. Không cần học toàn bộ phần Upgrade ngay.

`|` = ngắt nhẹ giữa các cụm ý. **Bold** = từ mang thông tin chính, nên nhấn rõ hơn. Không cần dừng lâu; chỉ cần chia câu để người nghe dễ theo dõi.

## Cách học bài này

1. Đọc phần **Core script** theo từng hàng: hiểu cột VI, rồi nói cột EN.
2. Đọc lại cột **EN — Thought Group**. Ưu tiên rõ ý → đúng nhịp → rồi mới tăng tốc.
3. Khi nói được cả 8 câu mà không nhìn tài liệu, bài hôm nay đã hoàn thành.
4. Chỉ sau đó mới học phần **Upgrade** nếu bạn còn muốn.

## 1. Core script — học trước

| Cue | VI | EN | EN — Thought Group |
| --- | --- | --- | --- |
| Bài toán | Bài toán này kiểm tra hai chuỗi có phải là anagram hay không. | This problem checks if two strings are anagrams. | This problem **CHECKS** \| if two strings are **ANAGRAMS**. |
| Kiểm tra sớm | Đầu tiên, nếu hai chuỗi có độ dài khác nhau, chúng không phải là anagram. | First, if the strings have different lengths, they are not anagrams. | **FIRST** \| if the strings have different **LENGTHS** \| they are not **ANAGRAMS**. |
| Cách làm | Em dùng một mảng có kích thước 26 để đếm ký tự. | I use an array of size 26 to count characters. | I use an **ARRAY** of size 26 \| to count **CHARACTERS**. |
| Chuỗi thứ nhất | Với chuỗi thứ nhất, em tăng count. | For the first string, I increase the count. | For the **FIRST STRING** \| I increase the **COUNT**. |
| Chuỗi thứ hai | Với chuỗi thứ hai, em giảm count. | For the second string, I decrease the count. | For the **SECOND STRING** \| I decrease the **COUNT**. |
| Kết quả | Nếu mọi count đều bằng 0, hai chuỗi là anagram. | If all counts are zero, the strings are anagrams. | If all counts are **ZERO** \| the strings are **ANAGRAMS**. |
| Time complexity | Ta duyệt cả hai chuỗi một lần, nên time complexity là `O(n)`. | We scan both strings once, so the time complexity is `O(n)`. | We scan both strings **ONCE** \| so the time complexity is **O(n)**. |
| Space complexity | Space complexity là `O(1)` vì mảng luôn có 26 phần tử. | The space complexity is `O(1)` because the array always has 26 elements. | The space complexity is **O(1)** \| because the array always has 26 **ELEMENTS**. |

### Bản shadowing

Đừng đọc mọi từ với cùng một lực. Ví dụ, thay vì đọc đều câu đầu, hãy nói: “This problem **CHECKS** | if two strings are **ANAGRAMS**.” Mỗi cụm ý ngắn chỉ cần một từ nổi bật.

```text
This problem CHECKS | if two strings are ANAGRAMS.
FIRST | if the strings have different LENGTHS | they are not ANAGRAMS.
I use an ARRAY of size 26 | to count CHARACTERS.
For the FIRST STRING | I increase the COUNT.
For the SECOND STRING | I decrease the COUNT.
If all counts are ZERO | the strings are ANAGRAMS.
We scan both strings ONCE | so the time complexity is O(n).
The space complexity is O(1) | because the array always has 26 ELEMENTS.
```

## 2. Core vocabulary — chỉ cần 5 cụm này

| English | Nghĩa tiếng Việt | Câu trong bài |
| --- | --- | --- |
| anagram | hai chuỗi có cùng ký tự và số lần xuất hiện | `The strings are anagrams.` |
| count | đếm / số lượng | `I increase the count.` |
| increase | tăng | `I increase the count.` |
| decrease | giảm | `I decrease the count.` |
| length | độ dài | `The strings have different lengths.` |

## 3. Upgrade — để sau khi Core đã trơn

### Approach 1: Brute force

| VI | EN |
| --- | --- |
| Một cách đơn giản là, với mỗi ký tự trong chuỗi thứ nhất, tìm một ký tự giống nó chưa được dùng trong chuỗi thứ hai. | A simple approach \| is to find a matching unused **CHARACTER** \| in the second string \| for each character in the first string. |
| Ở trường hợp xấu nhất, ta quét chuỗi thứ hai cho mỗi ký tự của chuỗi thứ nhất. Vì vậy, time complexity là `O(n²)`. | In the **WORST CASE** \| we scan the second string \| for every character in the first string. \| So the time complexity is **O(n²)**. |

### Approach 2: Sorting

| VI | EN |
| --- | --- |
| Một cách khác là sort cả hai chuỗi và so sánh chúng. | Another approach \| is to **SORT BOTH STRINGS** \| and compare them. |
| Sorting chi phối complexity, nên time complexity là `O(n log n)`. | Sorting takes the **MOST TIME** \| so the time complexity is **O(n log n)**. |

### Cách nói thêm khi đã thoải mái

| VI | EN |
| --- | --- |
| Ta không cần quan tâm đến thứ tự ký tự; ta chỉ cần số lần xuất hiện của chúng. | We do not care about \| the **ORDER** of the characters. \| We only care about \| how many times each character **APPEARS**. |
| Các ký tự tương ứng của hai chuỗi triệt tiêu lẫn nhau; vì vậy nếu mọi count trở về 0, hai chuỗi có cùng tần suất ký tự. | Characters from the two strings **CANCEL EACH OTHER OUT** \| so if every count returns to **ZERO** \| the strings have the same character frequencies. |
| Nếu input có các ký tự ngoài chữ cái thường, em sẽ dùng `HashMap` thay cho mảng. | If the input can contain characters beyond lowercase English letters \| I would use a **HASHMAP** \| instead of an array. |
| Với HashMap, time complexity vẫn là `O(n)`, nhưng space complexity phụ thuộc vào số ký tự khác nhau. | With a **HASHMAP** \| the time complexity is still **O(n)** \| but the space complexity depends on the number of distinct characters. |

## 4. Nhìn 8 câu như một reasoning chain

```text
Problem
Are the two strings anagrams?
    ↓
Early check
Different lengths → false
    ↓
Mechanism
First string → increase count
Second string → decrease count
    ↓
Invariant / result
Matching characters cancel each other out → all counts = 0 → anagram
    ↓
Complexity
Scan once → O(n)
Fixed array → O(1)
```

Đây là bản đơn giản của model: **Actor → Action → Mechanism → Result**. Khi trả lời interview, cố gắng nói đủ mối nối này thay vì chỉ nêu tên approach: “frequency counting is better.”

## 5. Checklist nhẹ nhàng

- [ ] Em nói được 8 câu Core mà không nhìn cột VI hoặc EN.
- [ ] Em nói lại được 8 câu với thought groups và từ khóa rõ ràng.
- [ ] Em hiểu và dùng được 5 cụm từ trong Core vocabulary.
- [ ] Em tự giải thích bằng tiếng Việt được vì sao mọi count phải bằng 0.
- [ ] Nếu còn sức, em học thêm một câu ở phần Upgrade.
