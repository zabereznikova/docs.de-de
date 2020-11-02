---
title: Überprüfung der Lokalisierbarkeit
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET], localization
- localizability [.NET]
- international applications [.NET], localizability
- globalization [.NET], localizability
- culture, localizability
- localization [.NET], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
ms.openlocfilehash: 6aa0588ea4baa00be476a05c335cf2abaa22aab4
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064157"
---
# <a name="localizability-review"></a><span data-ttu-id="3aed7-102">Überprüfung der Lokalisierbarkeit</span><span class="sxs-lookup"><span data-stu-id="3aed7-102">Localizability review</span></span>

<span data-ttu-id="3aed7-103">Die Überprüfung der Lokalisierbarkeit ist ein Zwischenschritt bei der Entwicklung einer weltweit einsetzbaren Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3aed7-103">The localizability review is an intermediate step in the development of a world-ready application.</span></span> <span data-ttu-id="3aed7-104">Dabei wird überprüft, ob eine globalisierte Anwendung für die Lokalisierung bereit ist, und es werden Code oder Aspekte der Benutzeroberfläche bezeichnet, die eine besondere Behandlung erfordern.</span><span class="sxs-lookup"><span data-stu-id="3aed7-104">It verifies that a globalized application is ready for localization and identifies any code or any aspects of the user interface that require special handling.</span></span> <span data-ttu-id="3aed7-105">Mit diesem Schritt wird zudem sichergestellt, dass beim Lokalisierungsprozess keine Funktionsfehler in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="3aed7-105">This step also helps ensure that the localization process will not introduce any functional defects into your application.</span></span> <span data-ttu-id="3aed7-106">Wenn Sie alle Probleme behoben haben, die bei der Überprüfung der Lokalisierbarkeit ausgelöst wurden, ist Ihre Anwendung für die Lokalisierung bereit.</span><span class="sxs-lookup"><span data-stu-id="3aed7-106">When all the issues raised by the localizability review have been addressed, your application is ready for localization.</span></span> <span data-ttu-id="3aed7-107">Bei einer gründlichen Überprüfung der Lokalisierbarkeit sollten Sie beim Lokalisierungsprozess nicht den Quellcode ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="3aed7-107">If the localizability review is thorough, you should not have to modify any source code during the localization process.</span></span>

<span data-ttu-id="3aed7-108">Die Überprüfung der Lokalisierbarkeit umfasst die folgenden drei Prüfungen:</span><span class="sxs-lookup"><span data-stu-id="3aed7-108">The localizability review consists of the following three checks:</span></span>

- [<span data-ttu-id="3aed7-109">Wurden die Globalisierungsempfehlungen implementiert?</span><span class="sxs-lookup"><span data-stu-id="3aed7-109">Are the globalization recommendations implemented?</span></span>](#global)

- [<span data-ttu-id="3aed7-110">Wurden kulturabhängige Features ordnungsgemäß behandelt?</span><span class="sxs-lookup"><span data-stu-id="3aed7-110">Are culture-sensitive features handled correctly?</span></span>](#culture)

- [<span data-ttu-id="3aed7-111">Haben Sie Ihre Anwendung mit internationalen Daten getestet?</span><span class="sxs-lookup"><span data-stu-id="3aed7-111">Have you tested your application with international data?</span></span>](#test)

<a name="global"></a>
## <a name="implement-globalization-recommendations"></a><span data-ttu-id="3aed7-112">Implementieren von Globalisierungsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="3aed7-112">Implement globalization recommendations</span></span>

<span data-ttu-id="3aed7-113">Wenn Sie Ihre Anwendung unter Berücksichtigung einer späteren Lokalisierung entworfen und entwickelt und dabei die im Artikel [Globalisierung](globalization.md) erläuterten Empfehlungen befolgt haben, sollte Ihre Anwendung der Überprüfung der Lokalisierbarkeit hinsichtlich der Qualitätssicherung größtenteils standhalten.</span><span class="sxs-lookup"><span data-stu-id="3aed7-113">If you have designed and developed your application with localization in mind, and if you have followed the recommendations discussed in the [Globalization](globalization.md) article, the localizability review will largely be a quality assurance pass.</span></span> <span data-ttu-id="3aed7-114">Andernfalls sollten Sie an dieser Stelle die Empfehlungen hinsichtlich einer [Globalisierung](globalization.md) lesen und implementieren und die Fehler im Quellcode, die eine Lokalisierung unmöglich machen, beheben.</span><span class="sxs-lookup"><span data-stu-id="3aed7-114">Otherwise, during this stage you should review and implement the recommendations for [globalization](globalization.md) and fix the errors in source code that prevent localization.</span></span>

<a name="culture"></a>
## <a name="handle-culture-sensitive-features"></a><span data-ttu-id="3aed7-115">Arbeiten mit kulturabhängigen Funktionen</span><span class="sxs-lookup"><span data-stu-id="3aed7-115">Handle culture-sensitive features</span></span>

<span data-ttu-id="3aed7-116">.NET bietet keine programmgesteuerte Unterstützung für viele Bereiche, die je nach Kultur variieren.</span><span class="sxs-lookup"><span data-stu-id="3aed7-116">.NET does not provide programmatic support in a number of areas that vary widely by culture.</span></span> <span data-ttu-id="3aed7-117">In den meisten Fällen müssen Sie benutzerdefinierten Code schreiben, um Featurebereiche wie folgt zu behandeln:</span><span class="sxs-lookup"><span data-stu-id="3aed7-117">In most cases, you have to write custom code to handle feature areas like the following:</span></span>

- <span data-ttu-id="3aed7-118">Adressen</span><span class="sxs-lookup"><span data-stu-id="3aed7-118">Addresses</span></span>

- <span data-ttu-id="3aed7-119">Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="3aed7-119">Telephone numbers</span></span>

- <span data-ttu-id="3aed7-120">Papierformate</span><span class="sxs-lookup"><span data-stu-id="3aed7-120">Paper sizes</span></span>

- <span data-ttu-id="3aed7-121">Maßeinheiten für Länge, Gewicht, Fläche, Volumen und Temperatur</span><span class="sxs-lookup"><span data-stu-id="3aed7-121">Units of measure used for lengths, weights, area, volume, and temperatures</span></span>

   <span data-ttu-id="3aed7-122">Obwohl .NET keine integrierte Unterstützung für die Konvertierung von Maßeinheiten bietet, können Sie anhand der Eigenschaft <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> feststellen, ob ein bestimmtes Land oder eine Region das metrische System verwendet. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3aed7-122">Although .NET does not offer built-in support for converting between units of measure, you can use the <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> property to determine whether a particular country or region uses the metric system, as the following example illustrates.</span></span>

   [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
   [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]

<a name="test"></a>
## <a name="test-your-application"></a><span data-ttu-id="3aed7-123">Die Anwendung testen</span><span class="sxs-lookup"><span data-stu-id="3aed7-123">Test your application</span></span>

<span data-ttu-id="3aed7-124">Vor der Lokalisierung Ihrer Anwendung sollten Sie sie mit internationalen Daten und internationalen Betriebssystemversionen testen.</span><span class="sxs-lookup"><span data-stu-id="3aed7-124">Before you localize your application, you should test it by using international data on international versions of the operating system.</span></span> <span data-ttu-id="3aed7-125">Obwohl der Großteil der Benutzeroberfläche zu diesem Zeitpunkt nicht lokalisiert ist, können Sie Probleme wie die folgenden erkennen:</span><span class="sxs-lookup"><span data-stu-id="3aed7-125">Although most of the user interface will not be localized at this point, you will be able to detect problems such as the following:</span></span>

- <span data-ttu-id="3aed7-126">Serialisierte Daten, die in verschiedenen Betriebssystemversionen nicht korrekt deserialisiert werden</span><span class="sxs-lookup"><span data-stu-id="3aed7-126">Serialized data that does not deserialize correctly across operating system versions.</span></span>

- <span data-ttu-id="3aed7-127">Numerische Daten, die nicht den Konventionen der aktuellen Kultur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3aed7-127">Numeric data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="3aed7-128">Beispiel: Zahlen werden möglicherweise mit ungenauen Gruppentrennzeichen, Dezimaltrennzeichen oder Währungssymbolen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3aed7-128">For example, numbers may be displayed with inaccurate group separators, decimal separators, or currency symbols.</span></span>

- <span data-ttu-id="3aed7-129">Datums- und Uhrzeitangaben, die nicht den Konventionen der aktuellen Kultur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3aed7-129">Date and time data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="3aed7-130">Beispiel: Zahlen für Monat und Tag werden möglicherweise in der falschen Reihenfolge angezeigt, Datumstrennzeichen werden evtl. falsch angezeigt oder die Zeitzoneninformationen sind möglicherweise falsch.</span><span class="sxs-lookup"><span data-stu-id="3aed7-130">For example, numbers that represent the month and day may appear in the wrong order, date separators may be incorrect, or time zone information may be incorrect.</span></span>

- <span data-ttu-id="3aed7-131">Ressourcen, die nicht gefunden werden können, weil Sie keine Standardkultur für Ihre Anwendung festgelegt haben</span><span class="sxs-lookup"><span data-stu-id="3aed7-131">Resources that cannot be found because you have not identified a default culture for your application.</span></span>

- <span data-ttu-id="3aed7-132">Zeichenfolgen, die in einer für die spezifische Kultur ungewöhnlichen Reihenfolge angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="3aed7-132">Strings that are displayed in an unusual order for the specific culture.</span></span>

- <span data-ttu-id="3aed7-133">Zeichenfolgenvergleiche oder Vergleiche im Hinblick auf Gleichheit, die unerwartete Ergebnisse zurückgeben</span><span class="sxs-lookup"><span data-stu-id="3aed7-133">String comparisons or comparisons for equality that return unexpected results.</span></span>

<span data-ttu-id="3aed7-134">Wenn Sie bei der Anwendungsentwicklung die Globalisierungsempfehlungen befolgt, kulturabhängige Features ordnungsgemäß behandelt und im Zuge von Tests Lokalisierungsprobleme ermittelt und behoben haben, können Sie mit dem nächsten Schritt der [Lokalisierung](localization.md) fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3aed7-134">If you've followed the globalization recommendations when developing your application, handled culture-sensitive features correctly, and identified and addressed the localization issues that arose during testing, you can proceed to the next step, [Localization](localization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3aed7-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aed7-135">See also</span></span>

- [<span data-ttu-id="3aed7-136">Globalisierung und Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="3aed7-136">Globalization and Localization</span></span>](index.md)
- [<span data-ttu-id="3aed7-137">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="3aed7-137">Localization</span></span>](localization.md)
- [<span data-ttu-id="3aed7-138">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="3aed7-138">Globalization</span></span>](globalization.md)
- [<span data-ttu-id="3aed7-139">Ressourcen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="3aed7-139">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
