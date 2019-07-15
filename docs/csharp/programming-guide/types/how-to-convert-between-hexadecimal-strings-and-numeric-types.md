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
ms.openlocfilehash: 2b896fb645113bc33b6a320948770947adc16dab
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661141"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="aeaf0-102">Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="aeaf0-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="aeaf0-103">In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="aeaf0-103">These examples show you how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="aeaf0-104">Abrufen des Hexadezimalwerts jedes Zeichens in einer [Zeichenfolge](../../../csharp/language-reference/keywords/string.md)</span><span class="sxs-lookup"><span data-stu-id="aeaf0-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
- <span data-ttu-id="aeaf0-105">Abrufen des [char](../../../csharp/language-reference/keywords/char.md), das jedem Wert in einer Hexadezimalzeichenfolge entspricht</span><span class="sxs-lookup"><span data-stu-id="aeaf0-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
- <span data-ttu-id="aeaf0-106">Konvertieren eines hexadezimalen `string` in [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="aeaf0-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
- <span data-ttu-id="aeaf0-107">Konvertieren eines hexadezimalen `string` in [float](../../../csharp/language-reference/builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="aeaf0-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/builtin-types/floating-point-numeric-types.md).</span></span>  
  
- <span data-ttu-id="aeaf0-108">Konvertieren eines [Byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)-Arrays in einen hexadezimalen `string`</span><span class="sxs-lookup"><span data-stu-id="aeaf0-108">Convert a [byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aeaf0-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aeaf0-109">Example</span></span>  
 <span data-ttu-id="aeaf0-110">In diesem Beispiel wird der Hexadezimalwert jedes Zeichens in einem `string` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="aeaf0-111">Zuerst wird der `string` in ein Array von Zeichen aufgegliedert.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="aeaf0-112">Danach wird <xref:System.Convert.ToInt32%28System.Char%29> auf jedem Zeichen aufgerufen, um dessen numerischen Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="aeaf0-113">Abschließend wird die Zahl als Hexadezimaldarstellung in einem `string` formatiert.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a><span data-ttu-id="aeaf0-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aeaf0-114">Example</span></span>  
 <span data-ttu-id="aeaf0-115">In diesem Beispiel wird ein `string` von Hexadezimalwerten analysiert, und die den einzelnen Hexadezimalwerten entsprechenden Zeichen werden ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-115">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="aeaf0-116">Zuerst wird die [Split(Char\[\])](xref:System.String.Split(System.Char[]))-Methode aufgerufen, um jeden Hexadezimalwert als einzelnen `string` in einem Array abzurufen.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-116">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="aeaf0-117">Anschließend wird <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> aufgerufen, damit der Hexadezimalwert in einen Dezimalwert konvertiert, der als [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) dargestellt wird. Es werden zwei verschiedene Arten gezeigt, um das diesem Zeichencode entsprechende Zeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-117">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="aeaf0-118">Die erste Methode verwendet <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, wodurch das Zeichen zurückgegeben wird, das dem ganzzahligen Argument als `string` entspricht.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-118">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="aeaf0-119">Die zweite Methode wandelt `int` explizit in ein [char](../../../csharp/language-reference/keywords/char.md) um.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-119">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a><span data-ttu-id="aeaf0-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aeaf0-120">Example</span></span>  
 <span data-ttu-id="aeaf0-121">Diese Beispiel stellt eine andere Möglichkeit dar, eine hexadezimale `string` in einen Integer zu konvertieren, indem die <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-121">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="aeaf0-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aeaf0-122">Example</span></span>  
 <span data-ttu-id="aeaf0-123">Das folgende Beispiel zeigt, wie eine hexadezimale `string` in [float](../../../csharp/language-reference/builtin-types/floating-point-numeric-types.md) konvertiert wird, indem die <xref:System.BitConverter?displayProperty=nameWithType>-Klasse und die <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-123">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/builtin-types/floating-point-numeric-types.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a><span data-ttu-id="aeaf0-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aeaf0-124">Example</span></span>  
 <span data-ttu-id="aeaf0-125">Das folgende Beispiel zeigt, wie Sie ein [Byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)-Array mithilfe der <xref:System.BitConverter?displayProperty=nameWithType>-Klasse in eine hexadezimale Zeichenfolge konvertieren.</span><span class="sxs-lookup"><span data-stu-id="aeaf0-125">The following example shows how to convert a [byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="aeaf0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aeaf0-126">See also</span></span>

- [<span data-ttu-id="aeaf0-127">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="aeaf0-127">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="aeaf0-128">Typen</span><span class="sxs-lookup"><span data-stu-id="aeaf0-128">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="aeaf0-129">Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt</span><span class="sxs-lookup"><span data-stu-id="aeaf0-129">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
