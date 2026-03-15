# ReactJS Interview Questions & Answers (Practice Guide)

## 1. ReactJS là gì? Nó khác gì so với JavaScript thuần?

**Trả lời:**\
ReactJS là một thư viện JavaScript dùng để xây dựng giao diện người dùng
(UI), đặc biệt cho các ứng dụng dạng Single Page Application (SPA).\
React được phát triển bởi Meta (Facebook) và hoạt động dựa trên kiến
trúc component giúp chia giao diện thành các phần nhỏ có thể tái sử
dụng.\
React sử dụng Virtual DOM để tối ưu việc cập nhật giao diện khi state
hoặc props thay đổi.

------------------------------------------------------------------------

## 2. Virtual DOM là gì?

**Trả lời:**\
Virtual DOM là một bản sao của DOM thật được biểu diễn dưới dạng các
object JavaScript.\
Khi state hoặc props thay đổi, React tạo một Virtual DOM mới và so sánh
với Virtual DOM cũ bằng thuật toán diffing.\
Sau đó React chỉ cập nhật những phần thay đổi lên DOM thật để tăng hiệu
năng.

------------------------------------------------------------------------

## 3. Sự khác nhau giữa props và state?

**Trả lời:**\
Props là dữ liệu được truyền từ component cha xuống component con và là
readonly.\
State là dữ liệu nội bộ của component và có thể thay đổi thông qua
setState hoặc useState.\
Khi state thay đổi, React sẽ re-render component để cập nhật giao diện.

------------------------------------------------------------------------

## 4. useState hoạt động như thế nào?

**Trả lời:**\
useState là một React Hook dùng để quản lý state trong function
component.\
Nó trả về một mảng gồm hai giá trị: giá trị state hiện tại và một hàm để
cập nhật state.\
Khi hàm cập nhật state được gọi, React sẽ re-render component.

``` javascript
const [count, setCount] = useState(0);
setCount(count + 1);
```

------------------------------------------------------------------------

## 5. useEffect dùng để làm gì?

**Trả lời:**\
useEffect được dùng để xử lý side effects trong React như gọi API, đăng
ký event, timer hoặc thao tác DOM.

Các trường hợp chạy: - Không có dependency → chạy sau mỗi render -
Dependency array rỗng `[]` → chạy 1 lần khi component mount - `[deps]` →
chạy khi dependency thay đổi

Có thể trả về cleanup function để chạy khi component unmount.

------------------------------------------------------------------------

## 6. Controlled vs Uncontrolled Component

**Trả lời:**

Controlled component: - Giá trị input được quản lý bởi React state -
Dùng `value` và `onChange`

``` javascript
<input value={name} onChange={(e)=>setName(e.target.value)} />
```

Uncontrolled component: - DOM tự quản lý giá trị - Dùng `ref` để truy
cập

``` javascript
<input ref={inputRef} />
```

------------------------------------------------------------------------

## 7. Key trong React list dùng để làm gì?

**Trả lời:**\
Key giúp React xác định identity của từng phần tử trong danh sách khi
diffing.\
Nhờ đó React biết phần tử nào được thêm, xóa hoặc thay đổi và chỉ cập
nhật những phần cần thiết.

------------------------------------------------------------------------

## 8. Component Lifecycle là gì?

**Trả lời:**

Lifecycle gồm 3 giai đoạn:

1.  Mount
2.  Update
3.  Unmount

Trong class component: - componentDidMount - componentDidUpdate -
componentWillUnmount

Trong function component dùng `useEffect` để thay thế lifecycle.

------------------------------------------------------------------------

## 9. Context API là gì?

**Trả lời:**\
Context API cho phép chia sẻ dữ liệu giữa nhiều component mà không cần
truyền props qua nhiều cấp.\
Context thường dùng cho:

-   theme
-   authentication
-   language
-   global settings

------------------------------------------------------------------------

## 10. React.memo vs useMemo vs useCallback

  Công cụ       Dùng để
  ------------- -------------------
  React.memo    memoize component
  useMemo       memoize giá trị
  useCallback   memoize function

Mục tiêu: tránh re-render không cần thiết.

------------------------------------------------------------------------

## 11. Redux dùng để làm gì?

**Trả lời:**\
Redux là thư viện quản lý global state.\
State được lưu trong một store và thay đổi thông qua action và reducer.

Redux giúp: - predictable state - debug dễ hơn - quản lý state phức tạp

------------------------------------------------------------------------

## 12. Cách tối ưu performance React app

Các kỹ thuật phổ biến:

### Tránh re-render không cần thiết

-   React.memo
-   useMemo
-   useCallback

### Code splitting

-   React.lazy
-   Suspense

### Virtualized list

-   react-window
-   react-virtualized

### Tối ưu assets

-   lazy load images
-   cache API

------------------------------------------------------------------------

## 13. Tại sao Hooks phải gọi đúng thứ tự?

**Trả lời:**\
React lưu state của Hook dựa trên thứ tự gọi trong quá trình render.\
Nếu Hook được đặt trong điều kiện hoặc vòng lặp, thứ tự gọi có thể thay
đổi khiến React ánh xạ sai state với Hook.

------------------------------------------------------------------------

## 14. React Reconciliation là gì?

**Trả lời:**\
Reconciliation là quá trình React so sánh Virtual DOM cũ và mới để xác
định những thay đổi cần cập nhật lên DOM thật.\
React sử dụng diffing algorithm để tìm sự khác biệt và chỉ cập nhật các
node cần thiết.

------------------------------------------------------------------------

## 15. Tại sao không nên dùng index làm key?

**Trả lời:**\
Index làm key có thể gây lỗi khi thêm, xóa hoặc reorder list.\
Vì index của các phần tử thay đổi khiến React nhầm identity của element
và reuse DOM sai.

------------------------------------------------------------------------

## 16. Tại sao setState bất đồng bộ?

**Trả lời:**\
React sử dụng batching để gom nhiều state update lại và render một lần
nhằm tăng performance.

``` javascript
setCount(c => c + 1);
setCount(c => c + 1);
```

Functional update đảm bảo state được cập nhật chính xác.

------------------------------------------------------------------------

## 17. Stale Closure là gì?

**Trả lời:**\
Stale closure xảy ra khi một function giữ reference của state cũ do
closure của JavaScript.

Ví dụ:

``` javascript
useEffect(() => {
  setInterval(() => {
    console.log(count);
  }, 1000);
}, []);
```

Callback giữ giá trị `count` ban đầu.

Cách fix: - thêm dependency - dùng useRef - dùng functional update

------------------------------------------------------------------------

# Tổng kết kiến thức quan trọng

### React Core

-   Components
-   Props vs State
-   Virtual DOM
-   Lifecycle

### Hooks

-   useState
-   useEffect
-   useMemo
-   useCallback
-   useContext

### Performance

-   React.memo
-   Code splitting
-   Virtualized list

### React Internals

-   Reconciliation
-   Hook order
-   Batching update
-   Stale closure
