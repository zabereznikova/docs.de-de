---
title: 'Gewusst wie: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
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
ms.openlocfilehash: 312b18e6bf30ace166435e51b1b83937b5c6bf38
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="ebb16-102">Gewusst wie: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ebb16-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="ebb16-103">In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="ebb16-103">These examples show you how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ebb16-104">Abrufen des Hexadezimalwerts jedes Zeichens in einer [Zeichenfolge](../../../csharp/language-reference/keywords/string.md)</span><span class="sxs-lookup"><span data-stu-id="ebb16-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
-   <span data-ttu-id="ebb16-105">Abrufen des [char](../../../csharp/language-reference/keywords/char.md), das jedem Wert in einer Hexadezimalzeichenfolge entspricht</span><span class="sxs-lookup"><span data-stu-id="ebb16-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
-   <span data-ttu-id="ebb16-106">Konvertieren eines hexadezimalen `string` in [int](../../../csharp/language-reference/keywords/int.md)</span><span class="sxs-lookup"><span data-stu-id="ebb16-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
-   <span data-ttu-id="ebb16-107">Konvertieren eines hexadezimalen `string` in [float](../../../csharp/language-reference/keywords/float.md)</span><span class="sxs-lookup"><span data-stu-id="ebb16-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md).</span></span>  
  
-   <span data-ttu-id="ebb16-108">Konvertieren eines [Byte](../../../csharp/language-reference/keywords/byte.md)-Arrays in einen hexadezimalen `string`</span><span class="sxs-lookup"><span data-stu-id="ebb16-108">Convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebb16-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebb16-109">Example</span></span>  
 <span data-ttu-id="ebb16-110">In diesem Beispiel wird der Hexadezimalwert jedes Zeichens in einem `string` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ebb16-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="ebb16-111">Zuerst wird der `string` in ein Array von Zeichen aufgegliedert.</span><span class="sxs-lookup"><span data-stu-id="ebb16-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="ebb16-112">Danach wird <xref:System.Convert.ToInt32%28System.Char%29> auf jedem Zeichen aufgerufen, um dessen numerischen Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ebb16-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="ebb16-113">Abschließend wird die Zahl als Hexadezimaldarstellung in einem `string` formatiert.</span><span class="sxs-lookup"><span data-stu-id="ebb16-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 <span data-ttu-id="ebb16-114">[!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ebb16-114">[!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebb16-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebb16-115">Example</span></span>  
 <span data-ttu-id="ebb16-116">In diesem Beispiel wird ein `string` von Hexadezimalwerten analysiert, und die den einzelnen Hexadezimalwerten entsprechenden Zeichen werden ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ebb16-116">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="ebb16-117">Zuerst wird die [Split(Char\[\])](xref:System.String.Split(System.Char[]))-Methode aufgerufen, um jeden Hexadezimalwert als einzelnen `string` in einem Array abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ebb16-117">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="ebb16-118">Anschließend wird <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> aufgerufen, damit der Hexadezimalwert in einen Dezimalwert konvertiert, der als [int](../../../csharp/language-reference/keywords/int.md) dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ebb16-118">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="ebb16-119">Es werden zwei verschiedene Arten gezeigt, um das diesem Zeichencode entsprechende Zeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ebb16-119">It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="ebb16-120">Die erste Methode verwendet <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, wodurch das Zeichen zurückgegeben wird, das dem ganzzahligen Argument als `string` entspricht.</span><span class="sxs-lookup"><span data-stu-id="ebb16-120">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="ebb16-121">Die zweite Methode wandelt `int` explizit in ein [char](../../../csharp/language-reference/keywords/char.md) um.</span><span class="sxs-lookup"><span data-stu-id="ebb16-121">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 <span data-ttu-id="ebb16-122">[!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ebb16-122">[!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebb16-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebb16-123">Example</span></span>  
 <span data-ttu-id="ebb16-124">Diese Beispiel stellt eine andere Möglichkeit dar, eine hexadezimale `string` in einen Integer zu konvertieren, indem die <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ebb16-124">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 <span data-ttu-id="ebb16-125">[!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ebb16-125">[!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebb16-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebb16-126">Example</span></span>  
 <span data-ttu-id="ebb16-127">Das folgende Beispiel zeigt, wie eine hexadezimale `string` in [float](../../../csharp/language-reference/keywords/float.md) konvertiert wird, indem die <xref:System.BitConverter?displayProperty=fullName>-Klasse und die <xref:System.Int32.Parse%2A?displayProperty=fullName>-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebb16-127">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md) by using the <xref:System.BitConverter?displayProperty=fullName> class and the <xref:System.Int32.Parse%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="ebb16-128">[!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="ebb16-128">[!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebb16-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebb16-129">Example</span></span>  
 <span data-ttu-id="ebb16-130">Das folgende Beispiel zeigt, wie Sie ein [Byte](../../../csharp/language-reference/keywords/byte.md)-Array mithilfe der <xref:System.BitConverter?displayProperty=fullName>-Klasse in eine hexadezimale Zeichenfolge konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ebb16-130">The following example shows how to convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=fullName> class.</span></span>  
  
 <span data-ttu-id="ebb16-131">[!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="ebb16-131">[!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb16-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebb16-132">See Also</span></span>  
 <span data-ttu-id="ebb16-133">[Standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md) </span><span class="sxs-lookup"><span data-stu-id="ebb16-133">[Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md) </span></span>  
 <span data-ttu-id="ebb16-134">[Typen](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="ebb16-134">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 [<span data-ttu-id="ebb16-135">Gewusst wie: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt</span><span class="sxs-lookup"><span data-stu-id="ebb16-135">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)

