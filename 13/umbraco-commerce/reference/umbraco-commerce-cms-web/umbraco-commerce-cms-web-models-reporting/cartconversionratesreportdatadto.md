---
title: CartConversionRatesReportDataDto
description: API reference for CartConversionRatesReportDataDto in Umbraco Commerce
---
## CartConversionRatesReportDataDto

```csharp
public class CartConversionRatesReportDataDto : ChartReportDataDto<decimal, long>
```

**Inheritance**

* Class [ChartReportDataDto&lt;TValue,TChartDataValue&gt;](chartreportdatadto-2.md)

**Namespace**
* [Umbraco.Commerce.Cms.Web.Models.Reporting](README.md)

### Constructors

#### CartConversionRatesReportDataDto

The default constructor.

```csharp
public CartConversionRatesReportDataDto()
```


### Properties

#### CurrentTotalCarts

```csharp
public long CurrentTotalCarts { get; set; }
```


---

#### PreviousTotalCarts

```csharp
public long? PreviousTotalCarts { get; set; }
```


---

#### TotalCartsFinalized

```csharp
public CartConversionRateDataDto TotalCartsFinalized { get; set; }
```


---

#### TotalCartsReachedCheckout

```csharp
public CartConversionRateDataDto TotalCartsReachedCheckout { get; set; }
```


<!-- DO NOT EDIT: generated by xmldocmd for Umbraco.Commerce.Cms.Web.dll -->