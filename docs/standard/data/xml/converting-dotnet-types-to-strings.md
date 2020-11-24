---
title: Konvertieren von .NET-Typen in Zeichenfolgen
ms.date: 03/30/2017
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: 9744224b4346b865a112b0eb6957f12553e1ec5f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830986"
---
# <a name="convert-net-types-to-strings"></a><span data-ttu-id="ee02c-102">Konvertieren von .NET-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ee02c-102">Convert .NET types to strings</span></span>

<span data-ttu-id="ee02c-103">Wenn Sie einen .NET-Typ in eine Zeichenfolge konvertieren möchten, verwenden Sie die **ToString**-Methode.</span><span class="sxs-lookup"><span data-stu-id="ee02c-103">If you want to convert a .NET type to a string, use the **ToString** method.</span></span> <span data-ttu-id="ee02c-104">Die **ToString**-Methode gibt eine Zeichenfolgendarstellung des eingelesenen Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="ee02c-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="ee02c-105">In der folgenden Tabelle sind die .NET-Typen aufgelistet, die eine Zeichenfolge in einem Format zurückgeben, das den Spezifikationen für das XML-Schema (XSD) entspricht.</span><span class="sxs-lookup"><span data-stu-id="ee02c-105">The following table lists the .NET types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="ee02c-106">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="ee02c-106">.NET type</span></span>|<span data-ttu-id="ee02c-107">Zurückgegebener Zeichenfolgentyp</span><span class="sxs-lookup"><span data-stu-id="ee02c-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="ee02c-108">Boolesch</span><span class="sxs-lookup"><span data-stu-id="ee02c-108">Boolean</span></span>|<span data-ttu-id="ee02c-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="ee02c-109">"true", "false"</span></span>|  
|<span data-ttu-id="ee02c-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="ee02c-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="ee02c-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="ee02c-111">"INF"</span></span>|  
|<span data-ttu-id="ee02c-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="ee02c-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="ee02c-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="ee02c-113">"-INF"</span></span>|  
|<span data-ttu-id="ee02c-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="ee02c-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="ee02c-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="ee02c-115">"INF"</span></span>|  
|<span data-ttu-id="ee02c-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="ee02c-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="ee02c-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="ee02c-117">"-INF"</span></span>|  
|<span data-ttu-id="ee02c-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="ee02c-118">DateTime</span></span>|<span data-ttu-id="ee02c-119">Das Format ist "jjjj-mm-ddTHH:mm:sszzzzzz" und die Teilmengen davon.</span><span class="sxs-lookup"><span data-stu-id="ee02c-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="ee02c-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="ee02c-120">Timespan</span></span>|<span data-ttu-id="ee02c-121">Das Format lautet PnYnMnTnHnMnS. Die bedeutet für `P2Y10M15DT10H30M20S` eine Dauer von 2 Jahren, 10 Monaten, 15 Tagen, 10 Stunden, 30 Minuten und 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="ee02c-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee02c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee02c-122">See also</span></span>

- [<span data-ttu-id="ee02c-123">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="ee02c-123">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)
- [<span data-ttu-id="ee02c-124">Konvertieren von Zeichenfolgen in .NET-Datentypen</span><span class="sxs-lookup"><span data-stu-id="ee02c-124">Converting Strings to .NET Data Types</span></span>](converting-strings-to-dotnet-data-types.md)
