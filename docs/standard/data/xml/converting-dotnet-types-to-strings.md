---
title: Konvertieren von .NET Framework-Typen in Zeichenfolgen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6ca134e13593fdacd759b0000e0e159f76ea067f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="f4fa2-102">Konvertieren von .NET Framework-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f4fa2-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="f4fa2-103">Wenn Sie einen .NET Framework-Typ in eine Zeichenfolge konvertieren möchten, verwenden Sie die **ToString**-Methode.</span><span class="sxs-lookup"><span data-stu-id="f4fa2-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="f4fa2-104">Die **ToString**-Methode gibt eine Zeichenfolgendarstellung des eingelesenen Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="f4fa2-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="f4fa2-105">In der folgenden Tabelle sind die .NET Framework-Typen aufgelistet, die eine Zeichenfolge in einem Format zurückgeben, das den Spezifikationen für das XML-Schema (XSD) entspricht.</span><span class="sxs-lookup"><span data-stu-id="f4fa2-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="f4fa2-106">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="f4fa2-106">.NET Framework type</span></span>|<span data-ttu-id="f4fa2-107">Zurückgegebener Zeichenfolgentyp</span><span class="sxs-lookup"><span data-stu-id="f4fa2-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="f4fa2-108">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f4fa2-108">Boolean</span></span>|<span data-ttu-id="f4fa2-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="f4fa2-109">"true", "false"</span></span>|  
|<span data-ttu-id="f4fa2-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="f4fa2-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="f4fa2-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="f4fa2-111">"INF"</span></span>|  
|<span data-ttu-id="f4fa2-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="f4fa2-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="f4fa2-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="f4fa2-113">"-INF"</span></span>|  
|<span data-ttu-id="f4fa2-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="f4fa2-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="f4fa2-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="f4fa2-115">"INF"</span></span>|  
|<span data-ttu-id="f4fa2-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="f4fa2-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="f4fa2-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="f4fa2-117">"-INF"</span></span>|  
|<span data-ttu-id="f4fa2-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="f4fa2-118">DateTime</span></span>|<span data-ttu-id="f4fa2-119">Das Format ist "jjjj-mm-ddTHH:mm:sszzzzzz" und die Teilmengen davon.</span><span class="sxs-lookup"><span data-stu-id="f4fa2-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="f4fa2-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="f4fa2-120">Timespan</span></span>|<span data-ttu-id="f4fa2-121">Das Format lautet PnYnMnTnHnMnS. Die bedeutet für `P2Y10M15DT10H30M20S` eine Dauer von 2 Jahren, 10 Monaten, 15 Tagen, 10 Stunden, 30 Minuten und 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="f4fa2-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4fa2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4fa2-122">See Also</span></span>  
 [<span data-ttu-id="f4fa2-123">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="f4fa2-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="f4fa2-124">Konvertieren von Zeichenfolgen in .NET Framework-Datentypen</span><span class="sxs-lookup"><span data-stu-id="f4fa2-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
