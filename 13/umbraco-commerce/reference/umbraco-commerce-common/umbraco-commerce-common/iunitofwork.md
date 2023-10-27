---
title: IUnitOfWork
description: API reference for IUnitOfWork in Umbraco Commerce
---
## IUnitOfWork

Defines a Unit of Work

```csharp
public interface IUnitOfWork : IDatabaseApiContainer, IDisposable, IScopedFactoryAccessor, 
    ITransactionApiContainer
```

**Inheritance**

* interface [IDatabaseApiContainer](idatabaseapicontainer.md)
* interface [IScopedFactoryAccessor](iscopedfactoryaccessor.md)
* interface [ITransactionApiContainer](itransactionapicontainer.md)

**Namespace**
* [Umbraco.Commerce.Common](README.md)

### Properties

#### Id

A unique ID for this Unit of Work

```csharp
public Guid Id { get; }
```


---

#### IsCompleted

Flag indicating whether this Unit of Work has completed

```csharp
public bool IsCompleted { get; }
```


---

#### IsDisposed

Flag indicating whether this Unit of Work has been disposed

```csharp
public bool IsDisposed { get; }
```


---

#### Items

A generic collection of items associated with this Unit of Work

```csharp
public Dictionary<string, object> Items { get; }
```


---

#### Options

The options for the unit of work

```csharp
public IUnitOfWorkOptions Options { get; }
```


---

#### Outer

A reference to an outer Unit of Work if this Unit of Work was created within an already open Unit of Work

```csharp
public IUnitOfWork Outer { get; }
```


### Methods

#### Complete

Marks the completion of a successful Unit of Work

```csharp
public void Complete()
```


---

#### Enlist

Enlist an item into this Unit of Work which will be notified of it's success or failure

```csharp
public void Enlist(string key, IUnitOfWorkEnlistable enlistable)
```


---

#### Enlist&lt;T&gt;

Enlist an item into this Unit of Work which will be notified of it's success or failure

```csharp
public void Enlist<T>(string key)
    where T : class, IUnitOfWorkEnlistable
```


---

#### GetEnlisted

Gets an enlisted item from the Unit of Work

```csharp
public object GetEnlisted(string key)
```


---

#### GetEnlisted&lt;T&gt;

Gets an enlisted item from the Unit of Work

```csharp
public T GetEnlisted<T>(string key)
    where T : class, IUnitOfWorkEnlistable
```


---

#### OnCompleted

Assign a callback function to run on Unit of Work completion

```csharp
public void OnCompleted(Func<Task> handler)
```


---

#### OnDisposed

Assign a callback functio to run on Unit of Work disposal

```csharp
public void OnDisposed(Func<Task> handler)
```


---

#### OnFailed

Assign a callback function to run on Unit of Work failure

```csharp
public void OnFailed(Func<Task> handler)
```


---

#### RollbackChanges

Rolls back any unpersisted changes

```csharp
public void RollbackChanges()
```


---

#### SaveChanges

Saves any active changes waiting to be persisted

```csharp
public void SaveChanges()
```


---

#### ScheduleNotification

Schedules a Notification Event to be raised once the Unit of Work is complete

```csharp
public void ScheduleNotification(INotificationEvent notificationEvent)
```

**Parameters**

| Parameter | Description |
| --- | --- |
| notificationEvent | The Notification Event to raise |


---

#### ScheduleNotifications (1 of 2)

Schedules a series of Notification Events to be raised once the Unit of Work is complete

```csharp
public void ScheduleNotifications(params INotificationEvent[] notificationEvents)
```

**Parameters**

| Parameter | Description |
| --- | --- |
| notificationEvents | The list of Notification Events to raise |

---

#### ScheduleNotifications (2 of 2)

Schedules a series of Notification Events to be raised once the Unit of Work is complete

```csharp
public void ScheduleNotifications(IEnumerable<INotificationEvent> notificationEvents)
```

**Parameters**

| Parameter | Description |
| --- | --- |
| notificationEvents | The list of Notification Events to raise |


<!-- DO NOT EDIT: generated by xmldocmd for Umbraco.Commerce.Common.dll -->