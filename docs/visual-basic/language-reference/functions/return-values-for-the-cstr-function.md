---
title: Rückgabewerte für die CStr-Funktion (Visual Basic)
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
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801529"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="66f0b-102">Rückgabewerte für die CStr-Funktion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66f0b-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="66f0b-103">Die folgende Tabelle beschreibt die Rückgabewerte für `CStr` für verschiedene Datentypen der `expression`.</span><span class="sxs-lookup"><span data-stu-id="66f0b-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="66f0b-104">Wenn `expression` Typ ist</span><span class="sxs-lookup"><span data-stu-id="66f0b-104">If `expression` type is</span></span>|<span data-ttu-id="66f0b-105">`CStr`-Rückgaben</span><span class="sxs-lookup"><span data-stu-id="66f0b-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="66f0b-106">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="66f0b-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="66f0b-107">Eine Zeichenfolge, die mit "True" oder "False".</span><span class="sxs-lookup"><span data-stu-id="66f0b-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="66f0b-108">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="66f0b-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="66f0b-109">Eine Zeichenfolge mit einem `Date` Wert (Datum und Uhrzeit), in dem kurzen Datumsformat Ihres Systems.</span><span class="sxs-lookup"><span data-stu-id="66f0b-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="66f0b-110">Numerische Datentypen</span><span class="sxs-lookup"><span data-stu-id="66f0b-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="66f0b-111">Eine Zeichenfolge, die die Anzahl darstellt.</span><span class="sxs-lookup"><span data-stu-id="66f0b-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="66f0b-112">Datum und die CStr</span><span class="sxs-lookup"><span data-stu-id="66f0b-112">CStr and Date</span></span>  
 <span data-ttu-id="66f0b-113">Die `Date` geben immer sowohl Datums-und Uhrzeitinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="66f0b-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="66f0b-114">Für Zwecke der typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1), werden eine *neutrale Wert* für das Datum und 00:00:00 (Mitternacht) einen neutralen Wert für die Zeit sein.</span><span class="sxs-lookup"><span data-stu-id="66f0b-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="66f0b-115">`CStr` umfasst nicht neutrale Werte in die resultierende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="66f0b-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="66f0b-116">Wenn Sie konvertieren, z. B. `#January 1, 0001 9:30:00#` in eine Zeichenfolge, das Ergebnis "9:30:00 Uhr"; die Datumsinformationen unterdrückt wird.</span><span class="sxs-lookup"><span data-stu-id="66f0b-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="66f0b-117">Die Datumsinformationen ist jedoch weiterhin vorhanden, in der ursprünglichen `Date` Wert und kann mit Funktionen wiederhergestellt werden, z. B. <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span><span class="sxs-lookup"><span data-stu-id="66f0b-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66f0b-118">Die `CStr` Funktion führt die Konvertierung, die basierend auf den Einstellungen der aktuellen Kultur für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="66f0b-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="66f0b-119">Um die Zeichenfolgendarstellung einer Zahl in einer bestimmten Kultur zu erhalten, verwenden Sie der Anzahl der `ToString(IFormatProvider)` Methode.</span><span class="sxs-lookup"><span data-stu-id="66f0b-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="66f0b-120">Verwenden Sie z. B. <xref:System.Double.ToString%2A?displayProperty=nameWithType> beim Konvertieren eines Werts vom Typ `Double` zu einem `String`.</span><span class="sxs-lookup"><span data-stu-id="66f0b-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f0b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66f0b-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="66f0b-122">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="66f0b-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="66f0b-123">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="66f0b-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="66f0b-124">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="66f0b-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
