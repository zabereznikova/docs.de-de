---
title: Rückgabewerte für die CStr-Funktion
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: cc5e5cc437175e9aebfba559488ca74283faa9ad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870161"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="5f1d3-102">Rückgabewerte für die CStr-Funktion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f1d3-102">Return Values for the CStr Function (Visual Basic)</span></span>

<span data-ttu-id="5f1d3-103">In der folgenden Tabelle werden die Rückgabewerte für `CStr` unterschiedliche Datentypen von beschrieben `expression` .</span><span class="sxs-lookup"><span data-stu-id="5f1d3-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="5f1d3-104">Wenn der `expression` Typ ist</span><span class="sxs-lookup"><span data-stu-id="5f1d3-104">If `expression` type is</span></span>|<span data-ttu-id="5f1d3-105">`CStr`-Rückgaben</span><span class="sxs-lookup"><span data-stu-id="5f1d3-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="5f1d3-106">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="5f1d3-106">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="5f1d3-107">Eine Zeichenfolge, die "true" oder "false" enthält.</span><span class="sxs-lookup"><span data-stu-id="5f1d3-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="5f1d3-108">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="5f1d3-108">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="5f1d3-109">Eine Zeichenfolge mit einem `Date` Wert (Datum und Uhrzeit) im kurzen Datumsformat Ihres Systems.</span><span class="sxs-lookup"><span data-stu-id="5f1d3-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="5f1d3-110">Numerische Datentypen</span><span class="sxs-lookup"><span data-stu-id="5f1d3-110">Numeric Data Types</span></span>](../../programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="5f1d3-111">Eine Zeichenfolge, die die Zahl darstellt.</span><span class="sxs-lookup"><span data-stu-id="5f1d3-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="5f1d3-112">CStr und Datum</span><span class="sxs-lookup"><span data-stu-id="5f1d3-112">CStr and Date</span></span>  

 <span data-ttu-id="5f1d3-113">Der- `Date` Typ enthält immer Datums-und Uhrzeit Informationen.</span><span class="sxs-lookup"><span data-stu-id="5f1d3-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="5f1d3-114">Für den Zweck der Typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1) als *neutralen Wert* für das Datum und 00:00:00 (Mitternacht) als neutralen Wert für die Zeit.</span><span class="sxs-lookup"><span data-stu-id="5f1d3-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="5f1d3-115">`CStr` schließt keine neutralen Werte in die resultierende Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="5f1d3-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="5f1d3-116">Wenn Sie z `#January 1, 0001 9:30:00#` . b. in eine Zeichenfolge konvertieren, ist das Ergebnis "9:30:00 am"; die Datumsinformationen werden unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="5f1d3-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="5f1d3-117">Die Datumsinformationen sind jedoch weiterhin im ursprünglichen `Date` Wert vorhanden und können mit Funktionen wie wieder hergestellt werden <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .</span><span class="sxs-lookup"><span data-stu-id="5f1d3-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f1d3-118">Die- `CStr` Funktion führt die Konvertierung basierend auf den aktuellen Kultur Einstellungen für die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="5f1d3-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="5f1d3-119">Um die Zeichen folgen Darstellung einer Zahl in einer bestimmten Kultur zu erhalten, verwenden Sie die-Methode der Zahl `ToString(IFormatProvider)` .</span><span class="sxs-lookup"><span data-stu-id="5f1d3-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="5f1d3-120">Verwenden Sie beispielsweise, <xref:System.Double.ToString%2A?displayProperty=nameWithType> Wenn Sie einen Wert vom Typ in einen-Wert umrechnen `Double` `String` .</span><span class="sxs-lookup"><span data-stu-id="5f1d3-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f1d3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f1d3-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="5f1d3-122">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="5f1d3-122">Type Conversion Functions</span></span>](type-conversion-functions.md)
- [<span data-ttu-id="5f1d3-123">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="5f1d3-123">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="5f1d3-124">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="5f1d3-124">Date Data Type</span></span>](../data-types/date-data-type.md)
