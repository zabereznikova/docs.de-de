---
title: Konvertieren von .NET Framework-Typen in Zeichenfolgen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: d232fb0e3ea4cf3189294d6e6f43ae9270417407
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287817"
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="1cdff-102">Konvertieren von .NET Framework-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1cdff-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="1cdff-103">Wenn Sie einen .NET Framework-Typ in eine Zeichenfolge konvertieren möchten, verwenden Sie die **ToString**-Methode.</span><span class="sxs-lookup"><span data-stu-id="1cdff-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="1cdff-104">Die **ToString**-Methode gibt eine Zeichenfolgendarstellung des eingelesenen Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="1cdff-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="1cdff-105">In der folgenden Tabelle sind die .NET Framework-Typen aufgelistet, die eine Zeichenfolge in einem Format zurückgeben, das den Spezifikationen für das XML-Schema (XSD) entspricht.</span><span class="sxs-lookup"><span data-stu-id="1cdff-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="1cdff-106">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="1cdff-106">.NET Framework type</span></span>|<span data-ttu-id="1cdff-107">Zurückgegebener Zeichenfolgentyp</span><span class="sxs-lookup"><span data-stu-id="1cdff-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="1cdff-108">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1cdff-108">Boolean</span></span>|<span data-ttu-id="1cdff-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="1cdff-109">"true", "false"</span></span>|  
|<span data-ttu-id="1cdff-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="1cdff-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="1cdff-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="1cdff-111">"INF"</span></span>|  
|<span data-ttu-id="1cdff-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="1cdff-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="1cdff-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="1cdff-113">"-INF"</span></span>|  
|<span data-ttu-id="1cdff-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="1cdff-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="1cdff-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="1cdff-115">"INF"</span></span>|  
|<span data-ttu-id="1cdff-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="1cdff-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="1cdff-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="1cdff-117">"-INF"</span></span>|  
|<span data-ttu-id="1cdff-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="1cdff-118">DateTime</span></span>|<span data-ttu-id="1cdff-119">Das Format ist "jjjj-mm-ddTHH:mm:sszzzzzz" und die Teilmengen davon.</span><span class="sxs-lookup"><span data-stu-id="1cdff-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="1cdff-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="1cdff-120">Timespan</span></span>|<span data-ttu-id="1cdff-121">Das Format lautet PnYnMnTnHnMnS. Die bedeutet für `P2Y10M15DT10H30M20S` eine Dauer von 2 Jahren, 10 Monaten, 15 Tagen, 10 Stunden, 30 Minuten und 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="1cdff-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cdff-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cdff-122">See also</span></span>

- [<span data-ttu-id="1cdff-123">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="1cdff-123">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)
- [<span data-ttu-id="1cdff-124">Konvertieren von Zeichenfolgen in .NET Framework-Datentypen</span><span class="sxs-lookup"><span data-stu-id="1cdff-124">Converting Strings to .NET Framework Data Types</span></span>](converting-strings-to-dotnet-data-types.md)
