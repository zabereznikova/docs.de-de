---
title: 'Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 046a406c32cd2ad0649cf88381a9e121f7566fe5
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423511"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="9dd83-102">Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9dd83-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="9dd83-103">In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="9dd83-103">These examples show you how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="9dd83-104">Abrufen des Hexadezimalwerts jedes Zeichens in einer [Zeichenfolge](../../../csharp/language-reference/keywords/string.md)</span><span class="sxs-lookup"><span data-stu-id="9dd83-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
- <span data-ttu-id="9dd83-105">Abrufen des [char](../../../csharp/language-reference/keywords/char.md), das jedem Wert in einer Hexadezimalzeichenfolge entspricht</span><span class="sxs-lookup"><span data-stu-id="9dd83-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
- <span data-ttu-id="9dd83-106">Konvertieren eines hexadezimalen `string` in [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="9dd83-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
- <span data-ttu-id="9dd83-107">Konvertieren eines hexadezimalen `string` in [float](../../../csharp/language-reference/keywords/float.md)</span><span class="sxs-lookup"><span data-stu-id="9dd83-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md).</span></span>  
  
- <span data-ttu-id="9dd83-108">Konvertieren eines [Byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)-Arrays in einen hexadezimalen `string`</span><span class="sxs-lookup"><span data-stu-id="9dd83-108">Convert a [byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dd83-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dd83-109">Example</span></span>  
 <span data-ttu-id="9dd83-110">In diesem Beispiel wird der Hexadezimalwert jedes Zeichens in einem `string` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9dd83-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="9dd83-111">Zuerst wird der `string` in ein Array von Zeichen aufgegliedert.</span><span class="sxs-lookup"><span data-stu-id="9dd83-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="9dd83-112">Danach wird <xref:System.Convert.ToInt32%28System.Char%29> auf jedem Zeichen aufgerufen, um dessen numerischen Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9dd83-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="9dd83-113">Abschließend wird die Zahl als Hexadezimaldarstellung in einem `string` formatiert.</span><span class="sxs-lookup"><span data-stu-id="9dd83-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a><span data-ttu-id="9dd83-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dd83-114">Example</span></span>  
 <span data-ttu-id="9dd83-115">In diesem Beispiel wird ein `string` von Hexadezimalwerten analysiert, und die den einzelnen Hexadezimalwerten entsprechenden Zeichen werden ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9dd83-115">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="9dd83-116">Zuerst wird die [Split(Char\[\])](xref:System.String.Split(System.Char[]))-Methode aufgerufen, um jeden Hexadezimalwert als einzelnen `string` in einem Array abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9dd83-116">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="9dd83-117">Anschließend wird <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> aufgerufen, damit der Hexadezimalwert in einen Dezimalwert konvertiert, der als [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) dargestellt wird. Es werden zwei verschiedene Arten gezeigt, um das diesem Zeichencode entsprechende Zeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9dd83-117">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="9dd83-118">Die erste Methode verwendet <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, wodurch das Zeichen zurückgegeben wird, das dem ganzzahligen Argument als `string` entspricht.</span><span class="sxs-lookup"><span data-stu-id="9dd83-118">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="9dd83-119">Die zweite Methode wandelt `int` explizit in ein [char](../../../csharp/language-reference/keywords/char.md) um.</span><span class="sxs-lookup"><span data-stu-id="9dd83-119">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a><span data-ttu-id="9dd83-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dd83-120">Example</span></span>  
 <span data-ttu-id="9dd83-121">Diese Beispiel stellt eine andere Möglichkeit dar, eine hexadezimale `string` in einen Integer zu konvertieren, indem die <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9dd83-121">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="9dd83-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dd83-122">Example</span></span>  
 <span data-ttu-id="9dd83-123">Das folgende Beispiel zeigt, wie eine hexadezimale `string` in [float](../../../csharp/language-reference/keywords/float.md) konvertiert wird, indem die <xref:System.BitConverter?displayProperty=nameWithType>-Klasse und die <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9dd83-123">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a><span data-ttu-id="9dd83-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dd83-124">Example</span></span>  
 <span data-ttu-id="9dd83-125">Das folgende Beispiel zeigt, wie Sie ein [Byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)-Array mithilfe der <xref:System.BitConverter?displayProperty=nameWithType>-Klasse in eine hexadezimale Zeichenfolge konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9dd83-125">The following example shows how to convert a [byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="9dd83-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dd83-126">See also</span></span>

- [<span data-ttu-id="9dd83-127">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="9dd83-127">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="9dd83-128">Typen</span><span class="sxs-lookup"><span data-stu-id="9dd83-128">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="9dd83-129">Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt</span><span class="sxs-lookup"><span data-stu-id="9dd83-129">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
