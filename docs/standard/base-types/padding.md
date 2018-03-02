---
title: "Auffüllen von Zeichenfolgen in .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea903c1f950e7c226e043c1fa7276a66126b2512
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="8f458-102">Auffüllen von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="8f458-102">Padding Strings in .NET</span></span>
<span data-ttu-id="8f458-103">Verwenden Sie eine der folgenden <xref:System.String>-Methoden, um eine neue Zeichenfolge zu erstellen, die aus einer ursprünglichen Zeichenfolge besteht, die mit voran- oder nachgestellten Zeichen auf eine angegebene Gesamtlänge aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="8f458-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="8f458-104">Als Auffüllzeichen können Leerzeichen oder ein angegebenes Zeichen verwendet werden, sodass die Zeichenfolge entweder rechtsbündig oder linksbündig ausgerichtet angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8f458-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="8f458-105">Methodenname</span><span class="sxs-lookup"><span data-stu-id="8f458-105">Method name</span></span>|<span data-ttu-id="8f458-106">Mit</span><span class="sxs-lookup"><span data-stu-id="8f458-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="8f458-107">Füllt eine Zeichenfolge mit vorangestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="8f458-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="8f458-108">Füllt eine Zeichenfolge mit nachgestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="8f458-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="8f458-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="8f458-109">PadLeft</span></span>  
 <span data-ttu-id="8f458-110">Die <xref:System.String.PadLeft%2A?displayProperty=nameWithType>-Methode erstellt eine neue Zeichenfolge durch Verkettung einer ausreichenden Anzahl vorangestellter Auffüllzeichen mit einer ursprünglichen Zeichenfolge, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="8f458-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="8f458-111">Die <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType>-Methode verwendet Leerzeichen als Auffüllzeichen, und mit der Methode <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> können Sie Ihre eigenen Auffüllzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="8f458-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="8f458-112">Im folgenden Codebeispiel wird über die Methode <xref:System.String.PadLeft%2A> eine neue Zeichenfolge erstellt, die 20 Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="8f458-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="8f458-113">In diesem Beispiel wird „`--------Hello World!`“ auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f458-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="8f458-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="8f458-114">PadRight</span></span>  
 <span data-ttu-id="8f458-115">Die <xref:System.String.PadRight%2A?displayProperty=nameWithType>-Methode erstellt eine neue Zeichenfolge durch Verkettung einer ausreichenden Anzahl nachgestellter Auffüllzeichen mit einer ursprünglichen Zeichenfolge, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="8f458-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="8f458-116">Die <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType>-Methode verwendet Leerzeichen als Auffüllzeichen, und mit der Methode <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> können Sie Ihre eigenen Auffüllzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="8f458-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="8f458-117">Im folgenden Codebeispiel wird über die Methode <xref:System.String.PadRight%2A> eine neue Zeichenfolge erstellt, die 20 Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="8f458-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="8f458-118">In diesem Beispiel wird „`Hello World!--------`“ auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f458-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8f458-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f458-119">See Also</span></span>  
 [<span data-ttu-id="8f458-120">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="8f458-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
