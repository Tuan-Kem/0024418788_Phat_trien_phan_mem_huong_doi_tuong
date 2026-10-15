# Sơ đồ lớp sơ bộ — EduHub

classDiagram
    class Student {
        +Guid Id
        +string StudentCode
        +string FullName
        +string Email
        +int DebtCount
        +Create(studentCode, fullName, email) Student
    }

    class ParkingCard {
        +Guid Id
        +string CardNumber
        +Guid StudentId
        +DateTime? ExpiryDate
        +bool IsActive
        +Create(cardNumber, studentId) ParkingCard
        +ExtendExpiry(days) void
        +SetStatus(isActive) void
    }

    class SubscriptionPackage {
        +Guid Id
        +string Name
        +int DurationDays
        +decimal Price
        +Create(name, durationDays, price) SubscriptionPackage
    }

    class Subscription {
        +Guid Id
        +Guid CardId
        +Guid PackageId
        +DateTime StartDate
        +DateTime EndDate
        +bool IsPaid
        +Create(cardId, packageId, durationDays) Subscription
    }

    class ParkingRecord {
        +Guid Id
        +Guid CardId
        +string LicensePlate
        +DateTime CheckInTime
        +DateTime? CheckOutTime
        +bool IsDebt
        +CreateCheckIn(cardId, licensePlate, isDebt) ParkingRecord
        +CheckOut() void
    }

    Student "1" -- "0..1" ParkingCard : FK_StudentId
    ParkingCard "1" -- "0..*" Subscription : FK_CardId
    SubscriptionPackage "1" -- "0..*" Subscription : FK_PackageId
    ParkingCard "1" -- "0..*" ParkingRecord : FK_CardId
