---
title: OrderTransactionChangeNotificationBase<TEntity>
description: API reference for OrderTransactionChangeNotificationBase<TEntity> in Umbraco Commerce
---
## OrderTransactionChangeNotificationBase&lt;TEntity&gt;

```csharp
public abstract class OrderTransactionChangeNotificationBase<TEntity> : 
    OrderNotificationEventBase<TEntity>
    where TEntity : OrderReadOnly
```

**Inheritance**

* class [OrderNotificationEventBase&lt;TOrder&gt;](ordernotificationeventbase-1.md)

**Namespace**
* [Umbraco.Commerce.Core.Events.Notification](README.md)

### Constructors

#### OrderTransactionChangeNotificationBase&lt;TEntity&gt;

```csharp
public OrderTransactionChangeNotificationBase(TEntity order, 
    ChangingValue<decimal> amountAuthorized, ChangingValue<decimal> transactionFee, 
    ChangingValue<string> transactionId, ChangingValue<PaymentStatus?> paymentStatus)
```


### Properties

#### AmountAuthorized

```csharp
public ChangingValue<decimal> AmountAuthorized { get; }
```


---

#### PaymentStatus

```csharp
public ChangingValue<PaymentStatus?> PaymentStatus { get; }
```


---

#### TransactionFee

```csharp
public ChangingValue<decimal> TransactionFee { get; }
```


---

#### TransactionId

```csharp
public ChangingValue<string> TransactionId { get; }
```


<!-- DO NOT EDIT: generated by xmldocmd for Umbraco.Commerce.Core.dll -->
