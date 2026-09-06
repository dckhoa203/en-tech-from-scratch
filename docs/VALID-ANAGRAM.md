# Valid Anagram

> Mục tiêu hôm nay: nói rõ cách giải tối ưu bằng 8 câu tiếng Anh đơn giản. Không cần học toàn bộ phần Upgrade ngay.

## Cách học bài này

1. Đọc phần **Core script** theo từng hàng: hiểu cột VI, rồi nói cột EN.
2. Khi nói được cả 8 câu mà không nhìn tài liệu, bài hôm nay đã hoàn thành.
3. Chỉ sau đó mới học phần **Upgrade** nếu bạn còn muốn.

## 1. Core script — học trước

| Cue | VI | EN |
| --- | --- | --- |
| Bài toán | Bài toán này kiểm tra hai chuỗi có phải là anagram hay không. | This problem checks if two strings are anagrams. |
| Kiểm tra sớm | Đầu tiên, nếu hai chuỗi có độ dài khác nhau, chúng không phải là anagram. | First, if the strings have different lengths, they are not anagrams. |
| Cách làm | Em dùng một mảng có kích thước 26 để đếm ký tự. | I use an array of size 26 to count characters. |
| Chuỗi thứ nhất | Với chuỗi thứ nhất, em tăng count. | For the first string, I increase the count. |
| Chuỗi thứ hai | Với chuỗi thứ hai, em giảm count. | For the second string, I decrease the count. |
| Kết quả | Nếu mọi count đều bằng 0, hai chuỗi là anagram. | If all counts are zero, the strings are anagrams. |
| Time complexity | Ta duyệt cả hai chuỗi một lần, nên time complexity là `O(n)`. | We scan both strings once, so the time complexity is `O(n)`. |
| Space complexity | Space complexity là `O(1)` vì mảng luôn có 26 phần tử. | The space complexity is `O(1)` because the array always has 26 elements. |

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
| Một cách đơn giản là, với mỗi ký tự trong chuỗi thứ nhất, tìm một ký tự giống nó chưa được dùng trong chuỗi thứ hai. | A simple approach is to find a matching unused character in the second string for each character in the first string. |
| Ở trường hợp xấu nhất, ta quét chuỗi thứ hai cho mỗi ký tự của chuỗi thứ nhất. Vì vậy, time complexity là `O(n²)`. | In the worst case, we scan the second string for every character in the first string. So the time complexity is `O(n²)`. |

### Approach 2: Sorting

| VI | EN |
| --- | --- |
| Một cách khác là sort cả hai chuỗi và so sánh chúng. | Another approach is to sort both strings and compare them. |
| Sorting chi phối complexity, nên time complexity là `O(n log n)`. | Sorting takes the most time, so the time complexity is `O(n log n)`. |

### Cách nói thêm khi đã thoải mái

| VI | EN |
| --- | --- |
| Ta không cần quan tâm đến thứ tự ký tự; ta chỉ cần số lần xuất hiện của chúng. | We do not care about the order of the characters. We only care about how many times each character appears. |
| Nếu input không chỉ có chữ cái thường, em sẽ dùng `HashMap` thay cho mảng. | If the input has more than lowercase letters, I would use a `HashMap` instead of an array. |
| Điều này đưa time complexity xuống `O(n)`. | This brings the time complexity down to `O(n)`. |

## 4. Checklist nhẹ nhàng

- [ ] Em nói được 8 câu Core mà không nhìn cột VI hoặc EN.
- [ ] Em hiểu và dùng được 5 cụm từ trong Core vocabulary.
- [ ] Em tự giải thích bằng tiếng Việt được vì sao mọi count phải bằng 0.
- [ ] Nếu còn sức, em học thêm một câu ở phần Upgrade.
