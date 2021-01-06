---
title: 'Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Konvertierungen zwischen Hexadezimalzeichenfolgen und numerischen Typen durchführen. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 18021156af879f324993beca04531c8a822725db
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513236"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="3ca7e-104">Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="3ca7e-104">How to convert between hexadecimal strings and numeric types (C# Programming Guide)</span></span>

<span data-ttu-id="3ca7e-105">In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="3ca7e-105">These examples show you how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="3ca7e-106">Abrufen des Hexadezimalwerts jedes Zeichens in einer [Zeichenfolge](../../language-reference/builtin-types/reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="3ca7e-106">Obtain the hexadecimal value of each character in a [string](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="3ca7e-107">Abrufen des [char](../../language-reference/builtin-types/char.md), das jedem Wert in einer Hexadezimalzeichenfolge entspricht</span><span class="sxs-lookup"><span data-stu-id="3ca7e-107">Obtain the [char](../../language-reference/builtin-types/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
- <span data-ttu-id="3ca7e-108">Konvertieren eines hexadezimalen `string` in [int](../../language-reference/builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="3ca7e-108">Convert a hexadecimal `string` to an [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
- <span data-ttu-id="3ca7e-109">Konvertieren eines hexadezimalen `string` in [float](../../language-reference/builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="3ca7e-109">Convert a hexadecimal `string` to a [float](../../language-reference/builtin-types/floating-point-numeric-types.md).</span></span>  
  
- <span data-ttu-id="3ca7e-110">Konvertieren eines [Byte](../../language-reference/builtin-types/integral-numeric-types.md)-Arrays in einen hexadezimalen `string`</span><span class="sxs-lookup"><span data-stu-id="3ca7e-110">Convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ca7e-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ca7e-111">Example</span></span>  

 <span data-ttu-id="3ca7e-112">In diesem Beispiel wird der Hexadezimalwert jedes Zeichens in einem `string` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-112">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="3ca7e-113">Zuerst wird der `string` in ein Array von Zeichen aufgegliedert.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-113">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="3ca7e-114">Danach wird <xref:System.Convert.ToInt32%28System.Char%29> auf jedem Zeichen aufgerufen, um dessen numerischen Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-114">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="3ca7e-115">Abschließend wird die Zahl als Hexadezimaldarstellung in einem `string` formatiert.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-115">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a><span data-ttu-id="3ca7e-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ca7e-116">Example</span></span>  

 <span data-ttu-id="3ca7e-117">In diesem Beispiel wird ein `string` von Hexadezimalwerten analysiert, und die den einzelnen Hexadezimalwerten entsprechenden Zeichen werden ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-117">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="3ca7e-118">Zuerst wird die [Split(Char\[\])](xref:System.String.Split(System.Char[]))-Methode aufgerufen, um jeden Hexadezimalwert als einzelnen `string` in einem Array abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-118">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="3ca7e-119">Anschließend wird <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> aufgerufen, damit der Hexadezimalwert in einen Dezimalwert konvertiert, der als [int](../../language-reference/builtin-types/integral-numeric-types.md) dargestellt wird. Es werden zwei verschiedene Arten gezeigt, um das diesem Zeichencode entsprechende Zeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-119">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../language-reference/builtin-types/integral-numeric-types.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="3ca7e-120">Die erste Methode verwendet <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, wodurch das Zeichen zurückgegeben wird, das dem ganzzahligen Argument als `string` entspricht.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-120">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="3ca7e-121">Die zweite Methode wandelt `int` explizit in ein [char](../../language-reference/builtin-types/char.md) um.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-121">The second technique explicitly casts the `int` to a [char](../../language-reference/builtin-types/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a><span data-ttu-id="3ca7e-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ca7e-122">Example</span></span>  

 <span data-ttu-id="3ca7e-123">Diese Beispiel stellt eine andere Möglichkeit dar, eine hexadezimale `string` in einen Integer zu konvertieren, indem die <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-123">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="3ca7e-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ca7e-124">Example</span></span>  

 <span data-ttu-id="3ca7e-125">Das folgende Beispiel zeigt, wie eine hexadezimale `string` in [float](../../language-reference/builtin-types/floating-point-numeric-types.md) konvertiert wird, indem die <xref:System.BitConverter?displayProperty=nameWithType>-Klasse und die <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-125">The following example shows how to convert a hexadecimal `string` to a [float](../../language-reference/builtin-types/floating-point-numeric-types.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a><span data-ttu-id="3ca7e-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ca7e-126">Example</span></span>  

 <span data-ttu-id="3ca7e-127">Das folgende Beispiel zeigt, wie Sie ein [Byte](../../language-reference/builtin-types/integral-numeric-types.md)-Array mithilfe der <xref:System.BitConverter?displayProperty=nameWithType>-Klasse in eine hexadezimale Zeichenfolge konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-127">The following example shows how to convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="3ca7e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ca7e-128">See also</span></span>

- [<span data-ttu-id="3ca7e-129">Standardmäßige Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="3ca7e-129">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="3ca7e-130">Typen</span><span class="sxs-lookup"><span data-stu-id="3ca7e-130">Types</span></span>](./index.md)
- [<span data-ttu-id="3ca7e-131">Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt</span><span class="sxs-lookup"><span data-stu-id="3ca7e-131">How to determine whether a string represents a numeric value</span></span>](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
