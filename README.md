# Advanced_JUnit_testing_practice
## Advanced JUnit testing practice with Java

Dưới đây là một bài tập kiểm thử nâng cao với JUnit, áp dụng cho một số thuật toán thông dụng với các cấu trúc điều khiển và kiểu dữ liệu phong phú. 

---

 **Đề bài**: 
Viết một chương trình Java thực hiện các chức năng sau:  
1. add(int a, int b): Trả về tổng của hai số.  
2. subtract(int a, int b): Trả về hiệu của hai số.  
3. multiply(int a, int b): Trả về tích của hai số.  
4. divide(int a, int b): Trả về thương của hai số. Nếu mẫu số bằng 0, ném ra ngoại lệ IllegalArgumentException. 

Yêu cầu:
- Viết kiểm thử đơn vị (unit test) cho từng phương thức trên bằng JUnit 5.
- Đảm bảo kiểm tra các trường hợp cơ bản và trường hợp ngoại lệ.

---

**Hướng dẫn giải:**

1. **Chương trình Java:**
```java
package org.example;

public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public int multiply(int a, int b) {
        return a * b;
    }

    public int divide(int a, int b) {
        if (b == 0) {
            throw new IllegalArgumentException("Cannot divide by zero.");
        }
        return a / b;
    }
}
```

---

2. **Bộ kiểm thử JUnit nâng cao:**

```java
import org.example.Calculator;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.*;

class CalculatorTest {

    private final Calculator calculator = new Calculator();

    @Test
    void testAdd() {
        assertEquals(5, calculator.add(2, 3));
        assertEquals(-1, calculator.add(2, -3));
        assertEquals(0, calculator.add(0, 0));
    }

    @Test
    void testSubtract() {
        assertEquals(1, calculator.subtract(3, 2));
        assertEquals(5, calculator.subtract(2, -3));
        assertEquals(0, calculator.subtract(0, 0));
    }

    @Test
    void testMultiply() {
        assertEquals(6, calculator.multiply(2, 3));
        assertEquals(-6, calculator.multiply(2, -3));
        assertEquals(0, calculator.multiply(2, 0));
    }

    @Test
    void testDivide() {
        assertEquals(2, calculator.divide(6, 3));
        assertEquals(-2, calculator.divide(6, -3));

        Exception exception = assertThrows(IllegalArgumentException.class, () -> calculator.divide(6, 0));
        assertEquals("Cannot divide by zero.", exception.getMessage());
    }
}
```

---

3. **Kết quả**
   
![image](https://github.com/user-attachments/assets/936bf562-80ef-44f7-90ec-8857916d5ebd)

**Độ Coverage**

![image](https://github.com/user-attachments/assets/659a54c4-1a4e-487e-b73a-d3f058f8819e)


---
4. **Tham khảo**
   
[Chat GPT](https://chatgpt.com/share/677c05a1-56bc-8005-8a52-ff4ef81b0502)
