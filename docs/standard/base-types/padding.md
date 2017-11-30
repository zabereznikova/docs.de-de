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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="f5850-102">Auffüllen von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="f5850-102">Padding Strings in .NET</span></span>
<span data-ttu-id="f5850-103">Verwenden Sie eine der folgenden <xref:System.String> Methoden zum Erstellen einer neuen Zeichenfolge, die der ursprünglichen Zeichenfolge, die aufgefüllt wird besteht, mit führenden oder nachgestellten Zeichen auf eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f5850-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="f5850-104">Als Auffüllzeichen können Leerzeichen oder ein angegebenes Zeichen verwendet werden, sodass die Zeichenfolge entweder rechtsbündig oder linksbündig ausgerichtet angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f5850-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="f5850-105">Methodenname</span><span class="sxs-lookup"><span data-stu-id="f5850-105">Method name</span></span>|<span data-ttu-id="f5850-106">Verwendung</span><span class="sxs-lookup"><span data-stu-id="f5850-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="f5850-107">Füllt eine Zeichenfolge mit vorangestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f5850-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="f5850-108">Füllt eine Zeichenfolge mit nachgestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f5850-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="f5850-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="f5850-109">PadLeft</span></span>  
 <span data-ttu-id="f5850-110">Die <xref:System.String.PadLeft%2A?displayProperty=nameWithType> Methode erstellt eine neue Zeichenfolge durch Verketten genügend führende Auffüllzeichen mit der ursprünglichen Zeichenfolge um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f5850-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="f5850-111">Die <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> Methode Leerzeichen als Auffüllzeichen verwendet und die <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> Methode können Sie eigene Auffüllzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="f5850-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="f5850-112">Im folgenden Codebeispiel wird mit der <xref:System.String.PadLeft%2A> Methode zum Erstellen einer neuen Zeichenfolge, die 20 Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="f5850-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="f5850-113">In diesem Beispiel wird „`--------Hello World!`“ auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5850-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="f5850-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="f5850-114">PadRight</span></span>  
 <span data-ttu-id="f5850-115">Die <xref:System.String.PadRight%2A?displayProperty=nameWithType> Methode erstellt eine neue Zeichenfolge durch Verketten genügend nachgestellte Auffüllzeichen mit der ursprünglichen Zeichenfolge um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f5850-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="f5850-116">Die <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> Methode Leerzeichen als Auffüllzeichen verwendet und die <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> Methode können Sie eigene Auffüllzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="f5850-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="f5850-117">Im folgenden Codebeispiel wird mit der <xref:System.String.PadRight%2A> Methode zum Erstellen einer neuen Zeichenfolge, die 20 Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="f5850-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="f5850-118">In diesem Beispiel wird „`Hello World!--------`“ auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5850-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f5850-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5850-119">See Also</span></span>  
 [<span data-ttu-id="f5850-120">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="f5850-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
