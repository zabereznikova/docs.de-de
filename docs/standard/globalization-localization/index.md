---
title: Globalisieren und Lokalisieren von .NET-Anwendungen
description: Erfahren Sie, wie Sie eine weltweit einsatzbereite Anwendung entwickeln. Außerdem erfahren Sie mehr über die Globalisierung, die Überprüfung der Lokalisierung und die Lokalisierung in .NET.
ms.date: 06/08/2018
helpviewer_keywords:
- international applications [.NET]
- globalization [.NET], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
ms.openlocfilehash: 670a159844cfeb475b26c1d1aa85e7f09a95c21f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829855"
---
# <a name="globalizing-and-localizing-net-applications"></a><span data-ttu-id="72b30-104">Globalisieren und Lokalisieren von .NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="72b30-104">Globalizing and localizing .NET applications</span></span>

<span data-ttu-id="72b30-105">Die Entwicklung einer weltweit einsetzbaren Anwendung, einschließlich einer Anwendung, die in eine oder mehrere Sprachen lokalisiert werden kann, umfasst drei Schritte: Globalisierung, Prüfung der Lokalisierbarkeit und Lokalisierung.</span><span class="sxs-lookup"><span data-stu-id="72b30-105">Developing a world-ready application, including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>

[<span data-ttu-id="72b30-106">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="72b30-106">Globalization</span></span>](globalization.md)

<span data-ttu-id="72b30-107">Dieser Schritt umfasst den Entwurf und die Codierung einer Anwendung, die kultur- und sprachneutral ist und die lokalisierten Benutzeroberflächen und regionalen Daten für alle Benutzer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="72b30-107">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="72b30-108">Er umfasst das Treffen von Entwurfs- und Programmierungsentscheidungen, die nicht auf kulturspezifischen Annahmen basieren.</span><span class="sxs-lookup"><span data-stu-id="72b30-108">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="72b30-109">Während eine globalisierte Anwendung nicht lokalisiert wird, wird sie dennoch so entworfen und geschrieben, dass sie anschließend relativ einfach in eine oder mehrere Sprachen lokalisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="72b30-109">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>

[<span data-ttu-id="72b30-110">Überprüfung der Lokalisierbarkeit</span><span class="sxs-lookup"><span data-stu-id="72b30-110">Localizability review</span></span>](localizability-review.md)

<span data-ttu-id="72b30-111">Dieser Schritt umfasst den Review des Codes und des Entwurfs einer Anwendung, um sicherzustellen, dass sie problemlos lokalisiert werden kann, und um mögliche Hindernisse für die Lokalisierung zu ermitteln. Es wird außerdem überprüft, ob der ausführbare Code der Anwendung von den Ressourcen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="72b30-111">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="72b30-112">Wenn die Globalisierungsphase effektiv war, bestätigt die Prüfung der Lokalisierbarkeit die Entwurfs- und Codierungsauswahlen, die während der Globalisierung getroffen wurden.</span><span class="sxs-lookup"><span data-stu-id="72b30-112">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="72b30-113">Die Lokalisierbarkeitsphase identifiziert möglicherweise auch alle verbleibenden Probleme, damit der Quellcode einer Anwendung nicht während der Lokalisierungsphase geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="72b30-113">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>

[<span data-ttu-id="72b30-114">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="72b30-114">Localization</span></span>](localization.md)

<span data-ttu-id="72b30-115">Dieser Schritt umfasst die Anpassung einer Anwendung an bestimmte Kulturen und Regionen.</span><span class="sxs-lookup"><span data-stu-id="72b30-115">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="72b30-116">Wenn die Globalisierungs- und Lokalisierbarkeitsschritte richtig durchgeführt wurden, sollte die Lokalisierung hauptsächlich die Übersetzung der Benutzeroberfläche umfassen.</span><span class="sxs-lookup"><span data-stu-id="72b30-116">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>

<span data-ttu-id="72b30-117">Die Befolgung dieser drei Schritte bietet zwei Vorteile:</span><span class="sxs-lookup"><span data-stu-id="72b30-117">Following these three steps provides two advantages:</span></span>

- <span data-ttu-id="72b30-118">Es ist keine Nachrüstung einer Anwendung mehr erforderlich, die nur eine Kultur, z. B. US-Englisch unterstützt, um zusätzliche Kulturen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="72b30-118">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>

- <span data-ttu-id="72b30-119">Dadurch ergeben sich lokalisierte Anwendungen, die stabiler sind und weniger Fehler haben.</span><span class="sxs-lookup"><span data-stu-id="72b30-119">It results in localized applications that are more stable and have fewer bugs.</span></span>

<span data-ttu-id="72b30-120">.NET bietet umfangreiche Unterstützung für die Entwicklung weltweit einsetzbarer und lokalisierter Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="72b30-120">.NET provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="72b30-121">Zahlreiche Typmember in der .NET-Klassenbibliothek vereinfachen die Globalisierung, indem sie Werte zurückgeben, die die Konventionen der Kultur des aktuellen Benutzers oder einer angegebenen Kultur widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="72b30-121">In particular, many type members in the .NET class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="72b30-122">Außerdem unterstützt .NET Satellitenassemblys, die den Lokalisierungsprozess einer Anwendung erleichtern.</span><span class="sxs-lookup"><span data-stu-id="72b30-122">Also, .NET supports satellite assemblies, which facilitate the process of localizing an application.</span></span>

<span data-ttu-id="72b30-123">Weitere Informationen finden Sie in der [Dokumentation zur Globalisierung](/globalization/).</span><span class="sxs-lookup"><span data-stu-id="72b30-123">For additional information, see the [Globalization documentation](/globalization/).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="72b30-124">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="72b30-124">In this section</span></span>

[<span data-ttu-id="72b30-125">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="72b30-125">Globalization</span></span>](globalization.md)

<span data-ttu-id="72b30-126">Erläutert die erste Phase der Erstellung einer weltweit einsetzbaren Anwendung, die das Entfernen und Codieren einer Anwendung involviert, die kultur- und sprachneutral ist.</span><span class="sxs-lookup"><span data-stu-id="72b30-126">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>

[<span data-ttu-id="72b30-127">.NET-Globalisierung und ICU</span><span class="sxs-lookup"><span data-stu-id="72b30-127">.NET globalization and ICU</span></span>](globalization-icu.md)

<span data-ttu-id="72b30-128">Hier wird beschrieben, wie [International Components for Unicode (ICU)](http://site.icu-project.org/home) bei der .NET-Globalisierung zum Einsatz kommen.</span><span class="sxs-lookup"><span data-stu-id="72b30-128">Describes how .NET globalization uses [International Components for Unicode (ICU)](http://site.icu-project.org/home).</span></span>

[<span data-ttu-id="72b30-129">Überprüfung der Lokalisierbarkeit</span><span class="sxs-lookup"><span data-stu-id="72b30-129">Localizability review</span></span>](localizability-review.md)

<span data-ttu-id="72b30-130">Erläutert die zweite Phase der Erstellung einer lokalisierten Anwendung, die das Identifizieren möglicher Hindernisse bei der Lokalisierung beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="72b30-130">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>

[<span data-ttu-id="72b30-131">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="72b30-131">Localization</span></span>](localization.md)

<span data-ttu-id="72b30-132">Erläutert die finale Phase der Erstellung einer lokalisierten Anwendung, die das Anpassen der Benutzeroberfläche einer Anwendung für bestimmte Bereiche oder Länder beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="72b30-132">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>

[<span data-ttu-id="72b30-133">Kulturunabhängige Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="72b30-133">Culture-insensitive string operations</span></span>](culture-insensitive-string-operations.md)

<span data-ttu-id="72b30-134">Beschreibt die Verwendung von standardmäßig kulturabhängigen .NET-Methoden und -Klassen zum Abrufen kulturunabhängiger Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="72b30-134">Describes how to use .NET methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>

[<span data-ttu-id="72b30-135">Empfehlungen für die Entwicklung weltweit einsatzfähiger Anwendungen</span><span class="sxs-lookup"><span data-stu-id="72b30-135">Best practices for developing world-ready applications</span></span>](best-practices-for-developing-world-ready-apps.md)

<span data-ttu-id="72b30-136">Beschreibt empfohlene Vorgehensweisen zur Durchführung der Globalisierung, Lokalisierung und Entwicklung weltweit einsatzfähiger ASP.NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="72b30-136">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>

## <a name="reference"></a><span data-ttu-id="72b30-137">Referenz</span><span class="sxs-lookup"><span data-stu-id="72b30-137">Reference</span></span>

- <span data-ttu-id="72b30-138"><xref:System.Globalization?displayProperty=nameWithType>-Namespace</span><span class="sxs-lookup"><span data-stu-id="72b30-138"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>

   <span data-ttu-id="72b30-139">Enthält Klassen, mit denen kulturbezogene Informationen definiert werden. Dazu zählen Sprache, Land/Region, verwendete Kalender, Formatierungsmuster für Datumsangaben, Währungen und Zahlen sowie die Sortierreihenfolge für Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="72b30-139">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>

- <span data-ttu-id="72b30-140"><xref:System.Resources>-Namespace</span><span class="sxs-lookup"><span data-stu-id="72b30-140"><xref:System.Resources> namespace</span></span>

   <span data-ttu-id="72b30-141">Stellt Klassen zum Erstellen, Bearbeiten und Verwenden von Ressourcen bereit.</span><span class="sxs-lookup"><span data-stu-id="72b30-141">Provides classes for creating, manipulating, and using resources.</span></span>

- <span data-ttu-id="72b30-142"><xref:System.Text>-Namespace</span><span class="sxs-lookup"><span data-stu-id="72b30-142"><xref:System.Text> namespace</span></span>

   <span data-ttu-id="72b30-143">Enthält Klassen, die die ASCII-, ANSI-, Unicode- und andere Zeichencodierungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="72b30-143">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>

- [<span data-ttu-id="72b30-144">Resgen.exe (Resource File Generator)</span><span class="sxs-lookup"><span data-stu-id="72b30-144">Resgen.exe (Resource File Generator)</span></span>](../../framework/tools/resgen-exe-resource-file-generator.md)

   <span data-ttu-id="72b30-145">Beschreibt die Verwendung von Resgen.exe zur Konvertierung von TXT-Dateien und RESX-Dateien (XML-basiertes Ressourcenformat) in binäre RESOURCES-Dateien der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="72b30-145">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>

- [<span data-ttu-id="72b30-146">Winres.exe (Windows Forms Resource Editor-Tool)</span><span class="sxs-lookup"><span data-stu-id="72b30-146">Winres.exe (Windows Forms Resource Editor)</span></span>](../../framework/tools/winres-exe-windows-forms-resource-editor.md)

   <span data-ttu-id="72b30-147">Beschreibt die Verwendung von Winres.exe zur Lokalisierung von Windows Forms-Formularen.</span><span class="sxs-lookup"><span data-stu-id="72b30-147">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>
