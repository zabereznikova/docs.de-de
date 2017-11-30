---
title: "Überprüfung der Lokalisierbarkeit"
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
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7633c7fe9e99bde96ee108460e983eff48f1c7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="localizability-review"></a><span data-ttu-id="557e9-102">Überprüfung der Lokalisierbarkeit</span><span class="sxs-lookup"><span data-stu-id="557e9-102">Localizability Review</span></span>
<span data-ttu-id="557e9-103">Die Prüfung der Lokalisierbarkeit ist ein Zwischenschritt bei der Entwicklung einer weltweit einsetzbaren Anwendung.</span><span class="sxs-lookup"><span data-stu-id="557e9-103">The localizability review is an intermediate step in the development of a world-ready application.</span></span> <span data-ttu-id="557e9-104">Er überprüft, ob eine globalisierte Anwendung ist bereit für die Lokalisierung bezeichnet jeglicher Code oder alle Aspekte der Benutzeroberfläche, die eine besondere Behandlung erfordern.</span><span class="sxs-lookup"><span data-stu-id="557e9-104">It verifies that a globalized application is ready for localization and identifies any code or any aspects of the user interface that require special handling.</span></span> <span data-ttu-id="557e9-105">Dieser Schritt wird auch sichergestellt, dass es sich bei der Lokalisierungsprozess Funktionsfehler nicht in die Anwendung integriert wird.</span><span class="sxs-lookup"><span data-stu-id="557e9-105">This step also helps ensure that the localization process will not introduce any functional defects into your application.</span></span> <span data-ttu-id="557e9-106">Wenn Sie alle Probleme, die ausgelöst wird, indem Sie die Prüfung der Lokalisierbarkeit behandelt wurden, ist Ihre Anwendung für die Lokalisierung bereit.</span><span class="sxs-lookup"><span data-stu-id="557e9-106">When all the issues raised by the localizability review have been addressed, your application is ready for localization.</span></span> <span data-ttu-id="557e9-107">Wenn die Prüfung der Lokalisierbarkeit umfassend ist, sollten Sie keiner Quellcode während des Lokalisierungsprozesses zu ändern.</span><span class="sxs-lookup"><span data-stu-id="557e9-107">If the localizability review is thorough, you should not have to modify any source code during the localization process.</span></span>  
  
 <span data-ttu-id="557e9-108">Die Prüfung der Lokalisierbarkeit umfasst die folgenden drei überprüft:</span><span class="sxs-lookup"><span data-stu-id="557e9-108">The localizability review consists of the following three checks:</span></span>  
  
-   [<span data-ttu-id="557e9-109">Werden die globalisierungsempfehlungen werden implementiert?</span><span class="sxs-lookup"><span data-stu-id="557e9-109">Are the globalization recommendations implemented?</span></span>](#global)  
  
-   [<span data-ttu-id="557e9-110">Werden kulturabhängigen Funktionen werden ordnungsgemäß behandelt?</span><span class="sxs-lookup"><span data-stu-id="557e9-110">Are culture-sensitive features handled correctly?</span></span>](#culture)  
  
-   [<span data-ttu-id="557e9-111">Haben Sie Ihre Anwendung mit internationalen Daten getestet?</span><span class="sxs-lookup"><span data-stu-id="557e9-111">Have you tested your application with international data?</span></span>](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a><span data-ttu-id="557e9-112">Implementieren von Globalisierungsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="557e9-112">Implementing globalization recommendations</span></span>  
 <span data-ttu-id="557e9-113">Wenn Sie entworfen und entwickelt von Ihrer Anwendung bei der Lokalisierung Bedenken haben und wenn Sie ausgeführt haben, werden die Empfehlungen im erläutert die [Globalisierung](../../../docs/standard/globalization-localization/globalization.md) Artikel, die Prüfung der Lokalisierbarkeit wird hauptsächlich Quality Assurance erfolgreich sein .</span><span class="sxs-lookup"><span data-stu-id="557e9-113">If you have designed and developed your application with localization in mind, and if you have followed the recommendations discussed in the [Globalization](../../../docs/standard/globalization-localization/globalization.md) article, the localizability review will largely be a quality assurance pass.</span></span> <span data-ttu-id="557e9-114">Andernfalls, während dieser Phase sollten Sie lesen und implementieren Sie die Empfehlungen für [Globalisierung](../../../docs/standard/globalization-localization/globalization.md), und beheben Sie die Fehler im Quellcode, die Lokalisierung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="557e9-114">Otherwise, during this stage you should review and implement the recommendations for [globalization](../../../docs/standard/globalization-localization/globalization.md), and fix the errors in source code that prevent localization.</span></span>  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a><span data-ttu-id="557e9-115">Arbeiten mit kulturabhängigen Funktionen</span><span class="sxs-lookup"><span data-stu-id="557e9-115">Handling culture-sensitive features</span></span>  
 <span data-ttu-id="557e9-116">.NET Framework bietet keine programmgesteuerte Unterstützung in verschiedenen Bereichen, die Kultur variieren.</span><span class="sxs-lookup"><span data-stu-id="557e9-116">The .NET Framework does not provide programmatic support in a number of areas that vary widely by culture.</span></span> <span data-ttu-id="557e9-117">In den meisten Fällen müssen Sie zum Schreiben von benutzerdefiniertem Code, um Funktionsbereiche wie folgt behandeln:</span><span class="sxs-lookup"><span data-stu-id="557e9-117">In most cases, you have to write custom code to handle feature areas like the following:</span></span>  
  
-   <span data-ttu-id="557e9-118">Adressen.</span><span class="sxs-lookup"><span data-stu-id="557e9-118">Addresses.</span></span>  
  
-   <span data-ttu-id="557e9-119">Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="557e9-119">Telephone numbers.</span></span>  
  
-   <span data-ttu-id="557e9-120">Papierformate.</span><span class="sxs-lookup"><span data-stu-id="557e9-120">Paper sizes.</span></span>  
  
-   <span data-ttu-id="557e9-121">Maßeinheiten für Längen, Gewichtungen, Bereich, Volume und Temperaturen verwendet.</span><span class="sxs-lookup"><span data-stu-id="557e9-121">Units of measure used for lengths, weights, area, volume, and temperatures.</span></span> <span data-ttu-id="557e9-122">Obwohl .NET Framework keine integrierten Unterstützung für die Konvertierung zwischen Maßeinheiten anbieten, können Sie die <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> -Eigenschaft können Sie bestimmen, ob ein bestimmtes Land oder eine Region das metrische System verwendet, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="557e9-122">Although the .NET Framework does not offer built-in support for converting between units of measure, you can use the <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> property to determine whether a particular country or region uses the metric system, as the following example illustrates.</span></span>  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a><span data-ttu-id="557e9-123">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="557e9-123">Testing your application</span></span>  
 <span data-ttu-id="557e9-124">Bevor Sie die Anwendung zu lokalisieren, sollten Sie es mit internationalen Daten in internationalen Versionen des Betriebssystems testen.</span><span class="sxs-lookup"><span data-stu-id="557e9-124">Before you localize your application, you should test it by using international data on international versions of the operating system.</span></span> <span data-ttu-id="557e9-125">Obwohl die meisten der Benutzeroberfläche zu diesem Zeitpunkt nicht lokalisiert werden, werden Sie z. B. die folgenden Probleme zu erkennen:</span><span class="sxs-lookup"><span data-stu-id="557e9-125">Although most of the user interface will not be localized at this point, you will be able to detect problems such as the following:</span></span>  
  
-   <span data-ttu-id="557e9-126">Serialisierte Daten, die bei Betriebssystemversionen nicht korrekt deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="557e9-126">Serialized data that does not deserialize correctly across operating system versions.</span></span>  
  
-   <span data-ttu-id="557e9-127">Numerische Daten, die nicht mit die Konventionen der aktuellen Kultur wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="557e9-127">Numeric data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="557e9-128">Beispielsweise können Zahlen mit ungenaue Gruppentrennzeichen, Dezimaltrennzeichen oder Währungssymbole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="557e9-128">For example, numbers may be displayed with inaccurate group separators, decimal separators, or currency symbols.</span></span>  
  
-   <span data-ttu-id="557e9-129">Datum und Uhrzeit-Daten, die nicht mit die Konventionen der aktuellen Kultur wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="557e9-129">Date and time data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="557e9-130">Z. B. Zahlen, die den Monat und Tag darstellen, möglicherweise in der falschen Reihenfolge angezeigt, Datumstrennzeichen ist möglicherweise falsch oder die Zeitzoneninformationen ist möglicherweise falsch.</span><span class="sxs-lookup"><span data-stu-id="557e9-130">For example, numbers that represent the month and day may appear in the wrong order, date separators may be incorrect, or time zone information may be incorrect.</span></span>  
  
-   <span data-ttu-id="557e9-131">Ressourcen, die nicht gefunden werden, weil Sie keine Standardkultur für die Anwendung identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="557e9-131">Resources that cannot be found because you have not identified a default culture for your application.</span></span>  
  
-   <span data-ttu-id="557e9-132">Zeichenfolgen, die in einer ungewöhnlichen Reihenfolge für die spezifische Kultur angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="557e9-132">Strings that are displayed in an unusual order for the specific culture.</span></span>  
  
-   <span data-ttu-id="557e9-133">Zeichenfolge vergleichen oder Vergleiche auf Gleichheit, die unerwartete Ergebnisse zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="557e9-133">String comparisons or comparisons for equality that return unexpected results.</span></span>  
  
 <span data-ttu-id="557e9-134">Wenn Sie haben die globalisierungsempfehlungen gefolgt, bei der Anwendungsentwicklung kulturabhängigen Funktionen ordnungsgemäß behandelt identifiziert und behandelt die Lokalisierungsprobleme, die während der Tests entstanden ist, können Sie mit dem nächsten Schritt fortfahren [Lokalisierung](../../../docs/standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="557e9-134">If you've followed the globalization recommendations when developing your application, handled culture-sensitive features correctly, and identified and addressed the localization issues that arose during testing, you can proceed to the next step, [Localization](../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="557e9-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="557e9-135">See Also</span></span>  
 [<span data-ttu-id="557e9-136">Globalisierung und Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="557e9-136">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="557e9-137">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="557e9-137">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 [<span data-ttu-id="557e9-138">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="557e9-138">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="557e9-139">Ressourcen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="557e9-139">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
