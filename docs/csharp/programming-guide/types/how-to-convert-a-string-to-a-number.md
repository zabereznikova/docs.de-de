---
title: 'Gewusst wie: Konvertieren einer Zeichenfolge in eine Zahl (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: 1f11ba3981b219d3b3a7817afd75fa78f2ccf78a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521752"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="fea92-102">Gewusst wie: Konvertieren einer Zeichenfolge in eine Zahl (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fea92-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="fea92-103">Sie können eine [Zeichenfolge](../../../csharp/language-reference/keywords/string.md) mithilfe von Methoden in der <xref:System.Convert>-Klasse oder durch die Verwendung der `TryParse`-Methode, die in verschiedenen numerischen Typen (int, long, float usw.) Anwendung findet, in eine Zahl umwandeln.</span><span class="sxs-lookup"><span data-stu-id="fea92-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="fea92-104">Wenn Sie über eine Zeichenfolge verfügen, ist es etwas effizienter und einfacher, eine `TryParse`-Methode (beispielsweise [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="fea92-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)).</span></span>  <span data-ttu-id="fea92-105">Die Verwendung einer <xref:System.Convert>-Methode eignet sich eher für allgemeine Objekte, die <xref:System.IConvertible> implementieren.</span><span class="sxs-lookup"><span data-stu-id="fea92-105">Using a <xref:System.Convert> method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="fea92-106">Sie können die Methode `Parse` oder `TryParse` für den numerischen Typ verwenden, den Sie in der Zeichenfolge erwarten, beispielsweise den <xref:System.Int32?displayProperty=nameWithType>-Typ.</span><span class="sxs-lookup"><span data-stu-id="fea92-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=nameWithType> type.</span></span>  <span data-ttu-id="fea92-107">Die <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType>-Methode verwendet <xref:System.Int32.Parse%2A> intern.</span><span class="sxs-lookup"><span data-stu-id="fea92-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="fea92-108">Wenn die Zeichenfolge in keinem gültigen Format vorliegt, löst `Parse` eine Ausnahme aus, während `TryParse` [false](../../../csharp/language-reference/keywords/false.md) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fea92-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fea92-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fea92-109">Example</span></span>  
 <span data-ttu-id="fea92-110">Die Methoden `Parse` und `TryParse` ignorieren Leerraum am Anfang und Ende der Zeichenfolge. Alle anderen Zeichen müssen jedoch Zeichen sein, die den entsprechenden numerischen Typ bilden (int, long, ulong, float, decimal usw.).</span><span class="sxs-lookup"><span data-stu-id="fea92-110">The `Parse` and `TryParse` methods ignore white space at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="fea92-111">Leerraum innerhalb der Zeichen, die die Zahl bilden, führen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="fea92-111">Any white space within the characters that form the number cause an error.</span></span>  <span data-ttu-id="fea92-112">Beispielsweise können Sie `decimal.TryParse` verwenden, um „10“, „10.3“, „  10  „ zu analysieren. Sie können diese Methode jedoch nicht verwenden, um 10 aus „10X“, „1 0“ (beachten Sie das Leerzeichen), „10 .3“ (beachten Sie das Leerzeichen), „10e1“ (`float.TryParse` funktioniert in diesem Fall) usw. zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="fea92-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="fea92-113">Die unten stehenden Beispiele zeigen erfolgreiche sowie nicht erfolgreiche Aufrufe von `Parse` und `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="fea92-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]  
[!code-csharp[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]  
[!code-csharp[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]  
[!code-csharp[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]  
[!code-csharp[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="fea92-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fea92-114">Example</span></span>  
 <span data-ttu-id="fea92-115">In der folgenden Tabelle werden einige der Methoden aus der <xref:System.Convert>-Klasse aufgelistet, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fea92-115">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="fea92-116">Numerischer Typ</span><span class="sxs-lookup"><span data-stu-id="fea92-116">Numeric Type</span></span>|<span data-ttu-id="fea92-117">Methode</span><span class="sxs-lookup"><span data-stu-id="fea92-117">Method</span></span>|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 <span data-ttu-id="fea92-118">In diesem Beispiel wird die <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType>-Methode aufgerufen, um einen Eingabe-[string](../../../csharp/language-reference/keywords/string.md) in einen [int](../../../csharp/language-reference/keywords/int.md)-Datentyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="fea92-118">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="fea92-119">Der Code fängt die zwei häufigsten Ausnahmen ab, die von dieser Methode ausgelöst werden können: <xref:System.FormatException> und <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="fea92-119">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="fea92-120">Wenn die Zahl inkrementiert werden kann, ohne dass der integer-Speicherbereich überläuft, fügt das Programm dem Ergebnis 1 hinzu und druckt die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fea92-120">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fea92-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fea92-121">See Also</span></span>

- [<span data-ttu-id="fea92-122">Typen</span><span class="sxs-lookup"><span data-stu-id="fea92-122">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
- [<span data-ttu-id="fea92-123">Gewusst wie: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt</span><span class="sxs-lookup"><span data-stu-id="fea92-123">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)  
- [<span data-ttu-id="fea92-124">.NET Framework 4-Hilfsprogramm zur Formatierung</span><span class="sxs-lookup"><span data-stu-id="fea92-124">.NET Framework 4 Formatting Utility</span></span>](https://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)
