---
title: 'Gewusst wie: Konvertieren einer Zeichenfolge in eine Zahl (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 08d13e40a385ce8e9011b508b04361b2e050f904
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="87ea0-102">Gewusst wie: Konvertieren einer Zeichenfolge in eine Zahl (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="87ea0-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="87ea0-103">Sie können eine [Zeichenfolge](../../../csharp/language-reference/keywords/string.md) mithilfe von Methoden in der <xref:System.Convert>-Klasse oder durch die Verwendung der `TryParse`-Methode, die in verschiedenen numerischen Typen (int, long, float usw.) Anwendung findet, in eine Zahl umwandeln.</span><span class="sxs-lookup"><span data-stu-id="87ea0-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="87ea0-104">Wenn Sie über eine Zeichenfolge verfügen, ist es etwas effizienter und einfacher, eine `TryParse`-Methode (beispielsweise `int.TryParse("11")`) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="87ea0-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, `int.TryParse("11")`).</span></span>  <span data-ttu-id="87ea0-105">Die Verwendung einer `Convert`-Methode eignet sich eher für allgemeine Objekte, die <xref:System.IConvertible> implementieren.</span><span class="sxs-lookup"><span data-stu-id="87ea0-105">Using a `Convert` method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="87ea0-106">Sie können die Methode `Parse` oder `TryParse` für den numerischen Typ verwenden, den Sie in der Zeichenfolge erwarten, beispielsweise den <xref:System.Int32?displayProperty=fullName>-Typ.</span><span class="sxs-lookup"><span data-stu-id="87ea0-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=fullName> type.</span></span>  <span data-ttu-id="87ea0-107">Die <xref:System.Convert.ToUInt32%2A?displayProperty=fullName>-Methode verwendet <xref:System.Int32.Parse%2A> intern.</span><span class="sxs-lookup"><span data-stu-id="87ea0-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="87ea0-108">Wenn die Zeichenfolge in keinem gültigen Format vorliegt, löst `Parse` eine Ausnahme aus, während `TryParse` [false](../../../csharp/language-reference/keywords/false.md) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="87ea0-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="87ea0-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87ea0-109">Example</span></span>  
 <span data-ttu-id="87ea0-110">Die Methoden `Parse` und `TryParse` ignorieren Leerzeichen am Anfang und Ende der Zeichenfolge. Alle anderen Zeichen müssen jedoch Zeichen sein, die den entsprechenden numerischen Typ bilden (int, long, ulong, float, decimal usw.).</span><span class="sxs-lookup"><span data-stu-id="87ea0-110">The `Parse` and `TryParse` methods ignore whitespace at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="87ea0-111">Leerzeichen in den die Zahl bildenden Zeichen führen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="87ea0-111">Any whitespace within the characters that form the number cause an error.</span></span>  <span data-ttu-id="87ea0-112">Beispielsweise können Sie `decimal.TryParse` verwenden, um „10“, „10.3“, „  10  „ zu analysieren. Sie können diese Methode jedoch nicht verwenden, um 10 aus „10X“, „1 0“ (beachten Sie das Leerzeichen), „10 .3“ (beachten Sie das Leerzeichen), „10e1“ (`float.TryParse` funktioniert in diesem Fall) usw. zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="87ea0-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="87ea0-113">Die unten stehenden Beispiele zeigen erfolgreiche sowie nicht erfolgreiche Aufrufe von `Parse` und `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="87ea0-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 <span data-ttu-id="87ea0-114">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ea0-114">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span></span>  
<span data-ttu-id="87ea0-115">[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ea0-115">[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]</span></span>  
<span data-ttu-id="87ea0-116">[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ea0-116">[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]</span></span>  
<span data-ttu-id="87ea0-117">[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ea0-117">[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]</span></span>  
<span data-ttu-id="87ea0-118">[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ea0-118">[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]</span></span>  
<span data-ttu-id="87ea0-119">[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ea0-119">[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="87ea0-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87ea0-120">Example</span></span>  
 <span data-ttu-id="87ea0-121">In der folgenden Tabelle werden einige der Methoden aus der <xref:System.Convert>-Klasse aufgelistet, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="87ea0-121">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="87ea0-122">Numerischer Typ</span><span class="sxs-lookup"><span data-stu-id="87ea0-122">Numeric Type</span></span>|<span data-ttu-id="87ea0-123">Methode</span><span class="sxs-lookup"><span data-stu-id="87ea0-123">Method</span></span>|  
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
  
 <span data-ttu-id="87ea0-124">In diesem Beispiel wird die <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName>-Methode aufgerufen, um einen Eingabe-[string](../../../csharp/language-reference/keywords/string.md) in einen [int](../../../csharp/language-reference/keywords/int.md)-Datentyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="87ea0-124">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="87ea0-125">Der Code fängt die zwei häufigsten Ausnahmen ab, die von dieser Methode ausgelöst werden können: <xref:System.FormatException> und <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="87ea0-125">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="87ea0-126">Wenn die Zahl inkrementiert werden kann, ohne dass der integer-Speicherbereich überläuft, fügt das Programm dem Ergebnis 1 hinzu und druckt die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="87ea0-126">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 <span data-ttu-id="87ea0-127">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ea0-127">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span></span>  
<span data-ttu-id="87ea0-128">[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ea0-128">[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ea0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87ea0-129">See Also</span></span>  
 <span data-ttu-id="87ea0-130">[Typen](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="87ea0-130">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="87ea0-131">[Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md) </span><span class="sxs-lookup"><span data-stu-id="87ea0-131">[How to: Determine Whether a String Represents a Numeric Value](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md) </span></span>  
 [<span data-ttu-id="87ea0-132">.NET Framework 4-Hilfsprogramm zur Formatierung</span><span class="sxs-lookup"><span data-stu-id="87ea0-132">.NET Framework 4 Formatting Utility</span></span>](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)

