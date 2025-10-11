- Mảng một chiều.

int[] array = new int[5]; string[] weekDays = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];

- Mảng nhiều chiều.

int[,] mang2chieu = { { 9, 99 }, { 3, 33 }, { 5, 55 } }; int[,,] mang3chieu = new int[,,] { { { 1, 2, 3 }, { 4, 5, 6 } }, { { 7, 8, 9 }, { 10, 11, 12 } } };

- Mảng của mảng (jagged array).

int[][] jaggedArray = new int[3][];
jaggedArray[0] = [1, 3, 5, 7, 9];
jaggedArray[1] = [0, 2, 4, 6];
jaggedArray[2] = [11, 22];
int[][] jaggedArray2 = [ [1, 3, 5, 7, 9], [0, 2, 4, 6], [11, 22] ];

Array là kiểu reference nên phải khởi tạo trước khi dùng.
mảng 2 chiều là jagged array luôn á
và jagged array thì có thể độ dài hàng khác nhau
còn mảng nhiều chiều thì độ dài hàng/cột phải bằng nhau
