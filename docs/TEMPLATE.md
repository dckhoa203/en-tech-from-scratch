# [TÊN BÀI TOÁN]

> Mục tiêu: dùng tài liệu này để luyện trình bày một bài coding interview bằng tiếng Anh. Đọc theo từng hàng: hiểu ý tiếng Việt, nói câu tiếng Anh, rồi tự nói lại không nhìn cột EN.

## 1. Problem snapshot

| Mục | Nội dung |
| --- | --- |
| Bài toán | `[Problem Name]` |
| Input / output | `[Mô tả ngắn input và output]` |
| Constraints quan trọng | `[Ví dụ: lowercase English letters, n <= ...]` |
| Ý tưởng tối ưu | `[Ví dụ: frequency counting]` |
| Độ phức tạp | `Time: O(...), Space: O(...)` |

## 2. Interview script

> Thay `[ ... ]` bằng nội dung của bài. Cột **Cue** là nhắc nhanh khi đang luyện; không cần đọc thành tiếng trong phỏng vấn.

| Cue | VI | EN |
| --- | --- | --- |
| Nhận dạng bài | Em nhận ra đây là một bài toán kinh điển về `[pattern/problem type]`. | I recognize this as a classic `[pattern/problem type]` problem. |
| Làm rõ giả định | Trước khi bắt đầu, em muốn xác nhận rằng `[assumption/constraint]`. | Before I start, I’d like to confirm that `[assumption/constraint]`. |
| Nêu kế hoạch | Trước khi viết code, em xin trình bày các hướng tiếp cận, từ đơn giản đến tối ưu. | Before jumping into the code, I’d like to walk through the approaches, from the simplest one to the optimal one. |
| Cách 1 | Cách đầu tiên là `[approach 1]`. Ý tưởng là `[core idea]`. | The first approach is `[approach 1]`. The idea is to `[core idea]`. |
| Phân tích cách 1 | Trong trường hợp xấu nhất, `[reason]`, nên time complexity là `O(...)`. | In the worst case, `[reason]`, so the time complexity is `O(...)`. |
| Trade-off 1 | Cách này trực quan nhưng `[limitation]`. | This approach is straightforward, but `[limitation]`. |
| Cách 2 | Một cách tốt hơn là `[approach 2]`. | A better approach is `[approach 2]`. |
| Phân tích cách 2 | Bước `[operation]` chi phối complexity, nên time complexity là `O(...)`. | The `[operation]` step dominates the complexity, so the time complexity is `O(...)`. |
| Chuyển ý | Tuy nhiên, điều bài toán thực sự cần là `[essential property]`. | However, what we really care about is `[essential property]`. |
| Cách tối ưu | Vì vậy, em sẽ dùng `[optimal approach]`. | So I’ll use `[optimal approach]`. |
| Các bước | Đầu tiên, em `[step 1]`. Sau đó, em `[step 2]`. Cuối cùng, em `[step 3]`. | First, I `[step 1]`. Then, I `[step 2]`. Finally, I `[step 3]`. |
| Tính đúng đắn | Nếu `[condition]`, thì `[conclusion]`; ngược lại, `[failure condition]`. | If `[condition]`, then `[conclusion]`; otherwise, `[failure condition]`. |
| Complexity | Ta duyệt input `[number]` lần, nên time complexity là `O(...)`. Space complexity là `O(...)` vì `[reason]`. | We scan the input `[number]` time(s), so the time complexity is `O(...)`. The space complexity is `O(...)` because `[reason]`. |
| Edge cases | Em cũng sẽ xử lý các edge case như `[case 1]` và `[case 2]`. | I’ll also handle edge cases such as `[case 1]` and `[case 2]`. |
| Chốt | Vì vậy, đây là approach em sẽ implement. | So this is the approach I would implement. |

## 3. Approach comparison

| Approach | Ý tưởng | Time | Space | Khi phù hợp / trade-off |
| --- | --- | --- | --- | --- |
| Brute force | `[idea]` | `O(...)` | `O(...)` | `[trade-off]` |
| Better | `[idea]` | `O(...)` | `O(...)` | `[trade-off]` |
| Optimal | `[idea]` | `O(...)` | `O(...)` | `[why chosen]` |

## 4. Vocabulary

| English | Nghĩa tiếng Việt | Cách dùng trong ngữ cảnh |
| --- | --- | --- |
| constraint | ràng buộc | `Given the constraint that ...` |
| straightforward | trực quan, dễ hiểu | `This approach is straightforward.` |
| dominate | chi phối | `Sorting dominates the complexity.` |
| frequency | tần suất / số lần xuất hiện | `We only care about character frequency.` |
| trade-off | sự đánh đổi | `The trade-off is extra space.` |
| edge case | trường hợp biên | `Let’s consider an edge case.` |

## 5. Useful chunks

| Chunk | Nghĩa / mục đích | Biến thể |
| --- | --- | --- |
| `I recognize this as a classic ... problem.` | Nhận dạng dạng bài | `This looks like a ... problem.` |
| `Before jumping into the code, I’d like to ...` | Dẫn vào phần giải thích | `Before implementing, let me ...` |
| `In the worst case, ...` | Phân tích trường hợp xấu nhất | `At worst, ...` |
| `What we really care about is ...` | Nêu tính chất cốt lõi | `The key observation is that ...` |
| `This gives us O(...) time.` | Kết luận complexity | `Therefore, the time complexity is O(...).` |

## 6. Key sentence structures

| Mục đích | Cấu trúc | Ví dụ |
| --- | --- | --- |
| Nêu giả định | `I’d like to confirm that + clause.` | `I’d like to confirm that the input contains only lowercase letters.` |
| Giải thích lý do | `Because + clause, ...` | `Because the array size is fixed, the space complexity is O(1).` |
| So sánh | `A better approach is to + verb.` | `A better approach is to sort both strings.` |
| Điều kiện | `If + present simple, ...` | `If every count is zero, the strings are anagrams.` |
| Chuyển ý | `However, what we really care about is + noun phrase.` | `However, what we really care about is character frequency.` |

## 7. Self-practice checklist

- [ ] Nói được phần tóm tắt bài toán và các assumptions trong 30 giây.
- [ ] So sánh được ít nhất hai approaches, kèm time/space complexity.
- [ ] Giải thích được vì sao approach tối ưu là đúng.
- [ ] Nêu được edge cases và ảnh hưởng của constraints.
- [ ] Nói lại toàn bộ cột EN mà không nhìn cột VI.
