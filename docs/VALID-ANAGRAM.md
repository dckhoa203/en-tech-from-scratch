# Valid Anagram

> Mục tiêu: luyện trình bày bài **Valid Anagram** theo format phỏng vấn song ngữ. Đọc từng hàng: hiểu ý tiếng Việt, nói câu tiếng Anh, rồi tự nói lại không nhìn cột EN.

## 1. Problem snapshot

| Mục | Nội dung |
| --- | --- |
| Bài toán | Kiểm tra hai chuỗi `s` và `t` có phải là anagram của nhau hay không. |
| Input / output | Input: hai chuỗi. Output: `true` nếu chúng chứa cùng các ký tự với cùng số lần xuất hiện; ngược lại là `false`. |
| Constraints quan trọng | Phiên bản cơ bản giả sử chỉ có lowercase English letters. |
| Ý tưởng tối ưu | Đếm tần suất ký tự bằng mảng `int[26]`. |
| Độ phức tạp | `Time: O(n), Space: O(1)` với alphabet gồm 26 chữ cái thường. |

## 2. Interview script

| Cue | VI | EN |
| --- | --- | --- |
| Nhận dạng bài | Em nhận ra đây là một bài toán kinh điển về kiểm tra tần suất ký tự. | I recognize this as a classic character-frequency problem. |
| Làm rõ giả định | Em giả sử hai chuỗi chỉ gồm các chữ cái tiếng Anh viết thường. | I’ll assume that both strings contain only lowercase English letters. |
| Kiểm tra sớm | Đầu tiên, nếu hai chuỗi có độ dài khác nhau thì chúng không thể là anagram. | First, if the two strings have different lengths, they cannot be anagrams. |
| Nêu kế hoạch | Trước khi viết code, em xin trình bày ba hướng tiếp cận, từ đơn giản đến tối ưu. | Before jumping into the code, I’d like to walk through three approaches, from the simplest one to the optimal one. |
| Cách 1 | Cách đầu tiên là brute force. Với mỗi ký tự của chuỗi thứ nhất, em tìm một ký tự tương ứng chưa được dùng trong chuỗi thứ hai. | The first approach is brute force. For each character in the first string, I look for a matching unused character in the second string. |
| Phân tích cách 1 | Ở trường hợp xấu nhất, em phải quét chuỗi thứ hai cho từng ký tự của chuỗi thứ nhất, nên time complexity là `O(n²)`. | In the worst case, I scan the second string for every character in the first string, so the time complexity is `O(n²)`. |
| Trade-off 1 | Cách này trực quan nhưng không scale tốt; em cũng cần theo dõi ký tự nào ở chuỗi thứ hai đã được ghép. | This approach is straightforward, but it does not scale well; I also need to track which characters in the second string have already been matched. |
| Cách 2 | Một cách tốt hơn là sort cả hai chuỗi rồi so sánh kết quả. Ví dụ, `"abc"` và `"cba"` đều trở thành `"abc"`. | A better approach is to sort both strings and then compare the results. For example, `"abc"` and `"cba"` both become `"abc"`. |
| Phân tích cách 2 | Nếu hai chuỗi đã sort bằng nhau thì chúng là anagram. Sorting chi phối complexity, nên time complexity là `O(n log n)`. | If the sorted strings are equal, they are anagrams. Sorting dominates the complexity, so the time complexity is `O(n log n)`. |
| Chuyển ý | Cách này clean, nhưng chúng ta không thực sự quan tâm đến thứ tự ký tự; điều cần biết là số lần xuất hiện của từng ký tự. | This solution is clean, but we do not actually care about character order; what we really care about is the frequency of each character. |
| Cách tối ưu | Vì vậy, em sẽ dùng frequency counting với một mảng `int[26]`. | So I’ll use frequency counting with an `int[26]` array. |
| Các bước | Khi duyệt chuỗi thứ nhất, em tăng count của ký tự tương ứng. Khi duyệt chuỗi thứ hai, em giảm count đó. | As I scan the first string, I increment the count for each character. As I scan the second string, I decrement the corresponding count. |
| Tính đúng đắn | Nếu mọi count đều bằng 0 ở cuối quá trình, mỗi ký tự xuất hiện cùng số lần trong hai chuỗi, nên chúng là anagram. Nếu có một count khác 0, chúng không phải là anagram. | If every count is zero at the end, each character appears the same number of times in both strings, so they are anagrams. If any count is nonzero, they are not anagrams. |
| Complexity | Ta duyệt mỗi chuỗi một lần, nên time complexity là `O(n)`. Mảng có kích thước cố định là 26, nên space complexity là `O(1)`. | We scan each string once, so the time complexity is `O(n)`. The array has a fixed size of 26, so the space complexity is `O(1)`. |
| Mở rộng | Nếu character set không bị giới hạn ở lowercase English letters, em sẽ dùng `HashMap` thay cho mảng. Khi đó space complexity là `O(k)`, với `k` là số ký tự phân biệt. | If the character set is not limited to lowercase English letters, I would use a `HashMap` instead of an array. Then the space complexity is `O(k)`, where `k` is the number of distinct characters. |
| Edge cases | Em đã xử lý trường hợp hai chuỗi có độ dài khác nhau, chuỗi rỗng, và các ký tự lặp lại. | This handles different string lengths, empty strings, and repeated characters. |
| Chốt | Vì vậy, frequency counting là approach em sẽ implement. | So frequency counting is the approach I would implement. |

## 3. Approach comparison

| Approach | Ý tưởng | Time | Space | Khi phù hợp / trade-off |
| --- | --- | --- | --- | --- |
| Brute force | Với mỗi ký tự ở `s`, tìm một ký tự giống nó chưa dùng ở `t`. | `O(n²)` | `O(n)` | Dễ hình dung nhưng chậm và phải đánh dấu phần tử đã ghép. |
| Sorting | Sort cả hai chuỗi rồi so sánh. | `O(n log n)` | Phụ thuộc cách sort / bản sao chuỗi | Code gọn, không cần giới hạn alphabet, nhưng làm nhiều hơn cần thiết. |
| Frequency counting | Tăng count khi duyệt `s`, giảm count khi duyệt `t`. | `O(n)` | `O(1)` với `int[26]` | Tối ưu khi input chỉ gồm lowercase English letters. |

## 4. Vocabulary

| English | Nghĩa tiếng Việt | Cách dùng trong ngữ cảnh |
| --- | --- | --- |
| anagram | từ/chuỗi đảo chữ; cùng ký tự với cùng tần suất | `The two strings are anagrams.` |
| character frequency | tần suất ký tự | `We compare character frequencies.` |
| matching unused character | ký tự tương ứng chưa được dùng | `I look for a matching unused character.` |
| increment / decrement | tăng / giảm | `I increment the count for s and decrement it for t.` |
| dominate | chi phối | `Sorting dominates the complexity.` |
| distinct | phân biệt, khác nhau | `k is the number of distinct characters.` |
| fixed size | kích thước cố định | `The array has a fixed size of 26.` |

## 5. Useful chunks

| Chunk | Nghĩa / mục đích | Biến thể |
| --- | --- | --- |
| `I recognize this as a classic character-frequency problem.` | Nhận dạng dạng bài | `This looks like a frequency-counting problem.` |
| `Before jumping into the code, I’d like to walk through ...` | Dẫn vào các hướng giải | `Before implementing, let me compare ...` |
| `In the worst case, ...` | Phân tích trường hợp xấu nhất | `At worst, ...` |
| `What we really care about is ...` | Nêu insight chính | `The key observation is that ...` |
| `If every count is zero at the end, ...` | Giải thích điều kiện đúng | `When all counts return to zero, ...` |
| `Sorting dominates the complexity.` | Nêu bottleneck | `The sorting step is the bottleneck.` |

## 6. Key sentence structures

| Mục đích | Cấu trúc | Ví dụ trong bài |
| --- | --- | --- |
| Nêu giả định | `I’ll assume that + clause.` | `I’ll assume that both strings contain only lowercase English letters.` |
| Loại trừ sớm | `If + clause, + result.` | `If the two strings have different lengths, they cannot be anagrams.` |
| Nêu cách làm | `For each + noun, I + verb.` | `For each character in the first string, I look for a match.` |
| Nêu lý do | `Because + clause, + result.` | `Because the array size is fixed, the space complexity is O(1).` |
| Nêu điều kiện | `If + present simple, + present simple.` | `If every count is zero, the strings are anagrams.` |
| Đưa phương án thay thế | `If + constraint changes, I would + verb.` | `If the character set is not limited, I would use a HashMap.` |

## 7. Self-practice checklist

- [ ] Tóm tắt bài toán và assumption về lowercase letters trong 30 giây.
- [ ] Giải thích được vì sao brute force phải đánh dấu ký tự đã ghép.
- [ ] So sánh được ba approaches và complexity của từng cách.
- [ ] Chứng minh được điều kiện “mọi count bằng 0”.
- [ ] Nêu được khi nào cần chuyển từ `int[26]` sang `HashMap`.
- [ ] Nói lại toàn bộ cột EN mà không nhìn cột VI.
