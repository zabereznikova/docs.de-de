---
title: Auffüllen von Zeichenfolgen in .NET
description: Erfahren Sie, wie Sie Zeichenfolgen in .NET auffüllen. Verwenden Sie die Methoden String.PadLeft und String.PadRight, um vorangestellte oder nachgestellte Zeichen zu ergänzen, sodass eine bestimmte Gesamtlänge erreicht wird.
ms.date: 03/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
ms.openlocfilehash: 5bf7023a3429e932a44ad0a0bd3409012f77cbf9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594529"
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="d9a1f-104">Auffüllen von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="d9a1f-104">Padding Strings in .NET</span></span>

<span data-ttu-id="d9a1f-105">Verwenden Sie eine der folgenden <xref:System.String>-Methoden, um eine neue Zeichenfolge zu erstellen, die aus einer ursprünglichen Zeichenfolge besteht, die mit voran- oder nachgestellten Zeichen auf eine angegebene Gesamtlänge aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-105">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="d9a1f-106">Es können entweder ein Leerraum oder ein anderes angegebenes Zeichen als Auffüllungszeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-106">The padding character can be a space or a specified character.</span></span> <span data-ttu-id="d9a1f-107">Die daraus entstehende Zeichenfolge wird entweder rechtsbündig oder linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-107">The resulting string appears to be either right-aligned or left-aligned.</span></span> <span data-ttu-id="d9a1f-108">Wenn die Länge der ursprünglichen Zeichenfolge bereits der gewünschten Gesamtlänge entspricht bzw. länger ist, geben die Auffüllmethoden die ursprüngliche Zeichenfolge unverändert zurück. Weitere Informationen finden Sie in den Abschnitten mit der **Rückgabe** der beiden Überladungen der Methoden <xref:System.String.PadLeft%2A?displayProperty=nameWithType> und <xref:System.String.PadRight%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-108">If the original string's length is already equal to or greater than the desired total length, the padding methods return the original string unchanged; for more information, see the **Returns** sections of the two overloads of the <xref:System.String.PadLeft%2A?displayProperty=nameWithType> and <xref:System.String.PadRight%2A?displayProperty=nameWithType> methods.</span></span>
  
|<span data-ttu-id="d9a1f-109">Methodenname</span><span class="sxs-lookup"><span data-stu-id="d9a1f-109">Method name</span></span>|<span data-ttu-id="d9a1f-110">Verwendung</span><span class="sxs-lookup"><span data-stu-id="d9a1f-110">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="d9a1f-111">Füllt eine Zeichenfolge mit vorangestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-111">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="d9a1f-112">Füllt eine Zeichenfolge mit nachgestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-112">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="d9a1f-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="d9a1f-113">PadLeft</span></span>  
 <span data-ttu-id="d9a1f-114">Die <xref:System.String.PadLeft%2A?displayProperty=nameWithType>-Methode erstellt eine neue Zeichenfolge durch Verkettung einer ausreichenden Anzahl vorangestellter Auffüllzeichen mit einer ursprünglichen Zeichenfolge, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-114">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="d9a1f-115">Die <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType>-Methode verwendet Leerzeichen als Auffüllzeichen, und mit der Methode <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> können Sie Ihre eigenen Auffüllzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-115">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="d9a1f-116">Im folgenden Codebeispiel wird über die Methode <xref:System.String.PadLeft%2A> eine neue Zeichenfolge erstellt, die 20 Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-116">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="d9a1f-117">In diesem Beispiel wird „`--------Hello World!`“ auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-117">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="d9a1f-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="d9a1f-118">PadRight</span></span>  
 <span data-ttu-id="d9a1f-119">Die <xref:System.String.PadRight%2A?displayProperty=nameWithType>-Methode erstellt eine neue Zeichenfolge durch Verkettung einer ausreichenden Anzahl nachgestellter Auffüllzeichen mit einer ursprünglichen Zeichenfolge, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-119">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="d9a1f-120">Die <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType>-Methode verwendet Leerzeichen als Auffüllzeichen, und mit der Methode <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> können Sie Ihre eigenen Auffüllzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-120">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="d9a1f-121">Im folgenden Codebeispiel wird über die Methode <xref:System.String.PadRight%2A> eine neue Zeichenfolge erstellt, die 20 Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-121">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="d9a1f-122">In diesem Beispiel wird „`Hello World!--------`“ auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d9a1f-122">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d9a1f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9a1f-123">See also</span></span>

- [<span data-ttu-id="d9a1f-124">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="d9a1f-124">Basic String Operations</span></span>](basic-string-operations.md)
