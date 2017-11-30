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
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3abe140e62f112a15a1ad1b1b2a79c14364b26d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="c493c-102">Konvertieren von .NET Framework-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c493c-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="c493c-103">Wenn .NET Framework-Typ in eine Zeichenfolge konvertiert werden sollen, verwenden Sie die **ToString** Methode.</span><span class="sxs-lookup"><span data-stu-id="c493c-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="c493c-104">Die **ToString** Methode gibt eine Zeichenfolgendarstellung des eingelesenen Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="c493c-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="c493c-105">In der folgenden Tabelle sind die .NET Framework-Typen aufgelistet, die eine Zeichenfolge in einem Format zurückgeben, das den Spezifikationen für das XML-Schema (XSD) entspricht.</span><span class="sxs-lookup"><span data-stu-id="c493c-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="c493c-106">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="c493c-106">.NET Framework type</span></span>|<span data-ttu-id="c493c-107">Zurückgegebener Zeichenfolgentyp</span><span class="sxs-lookup"><span data-stu-id="c493c-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="c493c-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="c493c-108">Boolean</span></span>|<span data-ttu-id="c493c-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="c493c-109">"true", "false"</span></span>|  
|<span data-ttu-id="c493c-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="c493c-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="c493c-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="c493c-111">"INF"</span></span>|  
|<span data-ttu-id="c493c-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="c493c-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="c493c-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="c493c-113">"-INF"</span></span>|  
|<span data-ttu-id="c493c-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="c493c-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="c493c-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="c493c-115">"INF"</span></span>|  
|<span data-ttu-id="c493c-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="c493c-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="c493c-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="c493c-117">"-INF"</span></span>|  
|<span data-ttu-id="c493c-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="c493c-118">DateTime</span></span>|<span data-ttu-id="c493c-119">Das Format ist "jjjj-mm-ddTHH:mm:sszzzzzz" und die Teilmengen davon.</span><span class="sxs-lookup"><span data-stu-id="c493c-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="c493c-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="c493c-120">Timespan</span></span>|<span data-ttu-id="c493c-121">Das Format lautet PnYnMnTnHnMnS. Die bedeutet für `P2Y10M15DT10H30M20S` eine Dauer von 2 Jahren, 10 Monaten, 15 Tagen, 10 Stunden, 30 Minuten und 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c493c-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c493c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c493c-122">See Also</span></span>  
 [<span data-ttu-id="c493c-123">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="c493c-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="c493c-124">Konvertieren von Zeichenfolgen in .NET Framework-Datentypen</span><span class="sxs-lookup"><span data-stu-id="c493c-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
