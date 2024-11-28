## Tổng hợp các ca sử dụng chính:
###  + PurchaseOder
###  + Employee
### + Timecard
### + Paycheck
### + BankSystem
### + ProjectManagementDatabase
## *1.Phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System.*
### *a. Paycheck (Bảng lương)*
### Bảng lương là kết quả của việc tính toán tiền lương dựa trên số giờ làm việc, lương cơ bản và các khoản hoa hồng. Bảng lương có thể được tạo và phân phối cho nhân viên vào các kỳ thanh toán định kỳ.
### Ca sử dụng:
- ### Run Payroll: Hệ thống tự động tính toán bảng lương cho tất cả nhân viên vào mỗi kỳ thanh toán (thứ Sáu hoặc cuối tháng). Hệ thống sử dụng thông tin từ bảng chấm công, đơn hàng mua (với nhân viên nhận hoa hồng), và các thông tin khác để tính toán.
- ### Generate Paycheck: Dựa trên các yếu tố như giờ làm việc, tỷ lệ lương, và hoa hồng (nếu có), hệ thống sẽ tạo bảng lương cho từng nhân viên và chuyển chúng đến hệ thống ngân hàng (cho các nhân viên chọn phương thức thanh toán chuyển khoản).
### Biểu đồ Sequence: 
![PlanText](https://www.planttext.com/api/plantuml/png/R94zJWD138NxEONBKEG2MwH9aA0YOYDHcrd3MfcVuF60zcmK78ahC9ja_nGwwytpzspFx_VFWTLH1JLzP0gMOCVuBkZXBGhiiRCjsQCnUnHbooSC2dMNbFn26erpyS2UB4gpT6QnBIPwaeR4c0jhlHcy5JoJ2jCdGPrVFQjICu66Ohsvz9tTMG8yn2m9Ng8SgHcPYwWPUD3X_91WrQ-wZTvpIXn32Rpt9nSxedHd5f2RtAaB7aF1UDHIJnDSprB15ftD3fN6Ky6g7zfrlG0m8vNCg-KcRkpzBsmOklnb6xycxuuKsINp1m00__y30000)
### *b. PurchaseOrder (Đơn hàng)*
### Đơn hàng là đối tượng được sử dụng bởi nhân viên có hoa hồng (Commissioned Employees) để ghi nhận các giao dịch bán hàng. Mỗi đơn hàng có thể được dùng để tính toán hoa hồng cho nhân viên.
### Ca sử dụng:
- ### Maintain Purchase Order: Nhân viên bán hàng có thể tạo, chỉnh sửa hoặc xóa các đơn hàng mà họ đã thực hiện trong hệ thống. Thông tin về khách hàng, sản phẩm bán, và ngày thực hiện sẽ được ghi lại.
- ### Calculate Commission: Các đơn hàng bán sẽ được dùng để tính hoa hồng cho nhân viên bán hàng. Tỷ lệ hoa hồng có thể dao động từ 10% đến 35% tùy theo chính sách của công ty.
### Biểu đồ Sequence: 
![PlanText](https://www.planttext.com/api/plantuml/png/f8wz3S8m44PxJt4Bi40AceIQI841JlO5Jl8VPoSIir4m4Yk055Caf03Hl_Uzxt6x7pXRgg2Zoq1U4pIC9q47VH1e1z5dJ0HxCIHAjIYPDKVq6UhW7AV4mPFPkMZ3bMW6lENYhl6RxGoge1R2JClk3FfmEXmB20rbP9kMmbhwrGg-Pt55dShcov_7Q7x-MPo_dquxHZq1003__mC0)
### *c. ProjectManagementDatabase (Cơ sở dữ liệu quản lý dự án)*
### Cơ sở dữ liệu này lưu trữ thông tin về các dự án, mã công việc, và các chi tiết liên quan. Các thông tin này sẽ được sử dụng trong bảng chấm công để phân bổ giờ làm việc cho các dự án cụ thể.
### Ca sử dụng:
- ### Maintain Timecard: Khi nhân viên ghi nhận giờ làm việc vào bảng chấm công, hệ thống sẽ lấy danh sách các mã công việc (charge number) từ cơ sở dữ liệu quản lý dự án để nhân viên có thể chọn mã phù hợp cho công việc mà họ đã làm.
### Biểu đồ Sequence: 
![PlanText](https://www.planttext.com/api/plantuml/png/V8p13O9G40NlLB4Dq0074YDN3L4QU7oVk8R_qMMXEG-MP0ic9XoCmUjaPbwFPwFUiv0ZxnDJe5IApX3bF9ZKDbmPV8U4Zf79ApXQZCoo6kOQz8RaqcXaW9s-u9zsyVDoLIhaG3VbJDbUO1rbFyMMDcQhILuktqyyMPBD3EtHzZ-JDm000F__0m00)
### *d. BankSystem (Hệ thống ngân hàng)*
### Hệ thống ngân hàng xử lý các giao dịch thanh toán cho nhân viên, đặc biệt là những nhân viên chọn phương thức thanh toán chuyển khoản trực tiếp.
### Ca sử dụng:
- ### Run Payroll: Sau khi tính toán bảng lương, hệ thống sẽ gửi thông tin thanh toán cho ngân hàng để xử lý các giao dịch chuyển khoản cho nhân viên chọn phương thức này.
- ### Process Payment: Hệ thống ngân hàng nhận thông tin từ hệ thống Payroll và thực hiện các giao dịch thanh toán cho nhân viên qua chuyển khoản ngân hàng.
### Biểu đồ Sequence: 
![PlanText](https://www.planttext.com/api/plantuml/png/X90x3i9034JxdC8b58YU8X8G2WgaY701Asl0Odzi7AISZO8ZSGMoV490I5Ih7StORtmzNpOicYPGqB4cMn9aZBk01hOkm0pjeMWg8PCaEGRXaZrQWONnsZL47-BJs9Vw-LTcb3wKk59JAP1ZOwWrhqZsJi4Wun3bZBohM60CAsJTFZcNXzeFaqTybBu6Jc0TsIk1gL8ix2ngMDgMts3ymI1M-Pmw_86J1tTYHNVeVhvR-6uJsQtgoFykUoVxs7DdjnnCDwOWgVsFUj--vw5QUt83003__mC0)
## *2.code Java mô phỏng ca sử dụng Maintain Timecard.
```markdown
```java
class Timecard {
    private String employeeId;
    private int hoursWorked;
    private boolean isSubmitted;

    public Timecard(String employeeId) {
        this.employeeId = employeeId;
        this.hoursWorked = 0;
        this.isSubmitted = false;
    }

    public void addHours(int hours) {
        if (isSubmitted) {
            System.out.println("Error: Timecard already submitted. Cannot add hours.");
            return;
        }
        if (hours < 0 || hours > 24) {
            System.out.println("Error: Hours must be between 0 and 24.");
            return;
        }
        this.hoursWorked += hours;
        System.out.println("Added " + hours + " hours. Total hours: " + this.hoursWorked);
    }

    public void submit() {
        if (isSubmitted) {
            System.out.println("Error: Timecard already submitted.");
            return;
        }
        isSubmitted = true;
        System.out.println("Timecard submitted successfully.");
    }

    public void display() {
        System.out.println("Timecard for Employee: " + employeeId);
        System.out.println("Total Hours Worked: " + hoursWorked);
        System.out.println("Status: " + (isSubmitted ? "Submitted" : "Draft"));
    }
}
public class Main {
    public static void main(String[] args) {
        Timecard timecard = new Timecard("E12345");

        timecard.addHours(8);
        timecard.addHours(6);
        timecard.display();
        timecard.submit();
        timecard.addHours(5);
        timecard.display();
    }
}
