---
title: Globalisieren und Lokalisieren von .NET Framework-Anwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- international applications [.NET Framework]
- globalization [.NET Framework], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET Framework], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
caps.latest.revision: "42"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 63f0e001280773c55f18f0604ca93986acbb9674
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2018
---
# <a name="globalizing-and-localizing-net-framework-applications"></a><span data-ttu-id="1e9c5-102">Globalisieren und Lokalisieren von .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="1e9c5-102">Globalizing and Localizing .NET Framework Applications</span></span>
<span data-ttu-id="1e9c5-103">Die Entwicklung einer [weltweit einsetzbaren Anwendung](http://msdn.microsoft.com/goglobal/bb978433.aspx), einschließlich einer Anwendung, die in eine oder mehrere Sprachen lokalisiert werden kann, umfasst drei Schritte: Globalisierung, Prüfung der Lokalisierbarkeit und Lokalisierung.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-103">Developing a [world-ready application](http://msdn.microsoft.com/goglobal/bb978433.aspx), including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>  
  
 [<span data-ttu-id="1e9c5-104">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="1e9c5-104">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="1e9c5-105">Dieser Schritt umfasst den Entwurf und die Codierung einer Anwendung, die kultur- und sprachneutral ist und die lokalisierten Benutzeroberflächen und regionalen Daten für alle Benutzer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-105">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="1e9c5-106">Er umfasst das Treffen von Entwurfs- und Programmierungsentscheidungen, die nicht auf kulturspezifischen Annahmen basieren.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-106">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="1e9c5-107">Während eine globalisierte Anwendung nicht lokalisiert wird, wird sie dennoch so entworfen und geschrieben, dass sie anschließend relativ einfach in eine oder mehrere Sprachen lokalisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-107">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>  
  
 [<span data-ttu-id="1e9c5-108">Überprüfung der Lokalisierbarkeit</span><span class="sxs-lookup"><span data-stu-id="1e9c5-108">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="1e9c5-109">Dieser Schritt umfasst den Review des Codes und des Entwurfs einer Anwendung, um sicherzustellen, dass sie problemlos lokalisiert werden kann, und um mögliche Hindernisse für die Lokalisierung zu ermitteln. Es wird außerdem überprüft, ob der ausführbare Code der Anwendung von den Ressourcen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-109">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="1e9c5-110">Wenn die Globalisierungsphase effektiv war, bestätigt die Prüfung der Lokalisierbarkeit die Entwurfs- und Codierungsauswahlen, die während der Globalisierung getroffen wurden.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-110">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="1e9c5-111">Die Lokalisierbarkeitsphase identifiziert möglicherweise auch alle verbleibenden Probleme, damit der Quellcode einer Anwendung nicht während der Lokalisierungsphase geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-111">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>  
  
 [<span data-ttu-id="1e9c5-112">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="1e9c5-112">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="1e9c5-113">Dieser Schritt umfasst die Anpassung einer Anwendung an bestimmte Kulturen und Regionen.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-113">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="1e9c5-114">Wenn die Globalisierungs- und Lokalisierbarkeitsschritte richtig durchgeführt wurden, sollte die Lokalisierung hauptsächlich die Übersetzung der Benutzeroberfläche umfassen.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-114">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>  
  
 <span data-ttu-id="1e9c5-115">Die Befolgung dieser drei Schritte bietet zwei Vorteile:</span><span class="sxs-lookup"><span data-stu-id="1e9c5-115">Following these three steps provides two advantages:</span></span>  
  
-   <span data-ttu-id="1e9c5-116">Es ist keine Nachrüstung einer Anwendung mehr erforderlich, die nur eine Kultur, z. B. US-Englisch unterstützt, um zusätzliche Kulturen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-116">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>  
  
-   <span data-ttu-id="1e9c5-117">Dadurch ergeben sich lokalisierte Anwendungen, die stabiler sind und weniger Fehler haben.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-117">It results in localized applications that are more stable and have fewer bugs.</span></span>  
  
 <span data-ttu-id="1e9c5-118">.NET Framework bietet umfangreiche Unterstützung für die Entwicklung weltweit einsetzbarer und lokalisierter Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-118">The .NET Framework provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="1e9c5-119">Zahlreiche Typmember in der .NET Framework-Klassenbibliothek vereinfachen die Globalisierung, indem sie Werte zurückgeben, die die Konventionen der Kultur des aktuellen Benutzers oder einer angegebenen Kultur widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-119">In particular, many type members in the .NET Framework class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="1e9c5-120">Außerdem unterstützt .NET Framework Satellitenassemblys, die den Lokalisierungsprozess einer Anwendung erleichtern.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-120">Also, the .NET Framework supports satellite assemblies, which facilitate the process of localizing an application.</span></span>  
  
 <span data-ttu-id="1e9c5-121">Weitere Informationen finden Sie in der [Dokumentation zur Globalisierung](/globalization/).</span><span class="sxs-lookup"><span data-stu-id="1e9c5-121">For additional information, see the [Globalization documentation](/globalization/).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e9c5-122">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1e9c5-122">In This Section</span></span>  
 [<span data-ttu-id="1e9c5-123">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="1e9c5-123">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="1e9c5-124">Erläutert die erste Phase der Erstellung einer weltweit einsetzbaren Anwendung, die das Entfernen und Codieren einer Anwendung involviert, die kultur- und sprachneutral ist.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-124">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>  
  
 [<span data-ttu-id="1e9c5-125">Überprüfung der Lokalisierbarkeit</span><span class="sxs-lookup"><span data-stu-id="1e9c5-125">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="1e9c5-126">Erläutert die zweite Phase der Erstellung einer lokalisierten Anwendung, die das Identifizieren möglicher Hindernisse bei der Lokalisierung beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-126">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>  
  
 [<span data-ttu-id="1e9c5-127">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="1e9c5-127">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="1e9c5-128">Erläutert die finale Phase der Erstellung einer lokalisierten Anwendung, die das Anpassen der Benutzeroberfläche einer Anwendung für bestimmte Bereiche oder Länder beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-128">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>  
  
 [<span data-ttu-id="1e9c5-129">Kulturunabhängige Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="1e9c5-129">Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="1e9c5-130">Beschreibt die Verwendung von standardmäßig kulturabhängigen .NET Framework-Methoden und -Klassen zum Abrufen kulturunabhängiger Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-130">Describes how to use .NET Framework methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>  
  
 [<span data-ttu-id="1e9c5-131">Empfehlungen für die Entwicklung weltweit einsatzfähiger Anwendungen</span><span class="sxs-lookup"><span data-stu-id="1e9c5-131">Best Practices for Developing World-Ready Applications</span></span>](../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)  
 <span data-ttu-id="1e9c5-132">Beschreibt empfohlene Vorgehensweisen zur Durchführung der Globalisierung, Lokalisierung und Entwicklung weltweit einsatzfähiger ASP.NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-132">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1e9c5-133">Verweis</span><span class="sxs-lookup"><span data-stu-id="1e9c5-133">Reference</span></span>  
 <span data-ttu-id="1e9c5-134"><xref:System.Globalization?displayProperty=nameWithType>-Namespace</span><span class="sxs-lookup"><span data-stu-id="1e9c5-134"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>  
 <span data-ttu-id="1e9c5-135">Enthält Klassen, mit denen kulturbezogene Informationen definiert werden. Dazu zählen Sprache, Land/Region, verwendete Kalender, Formatierungsmuster für Datumsangaben, Währungen und Zahlen sowie die Sortierreihenfolge für Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-135">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>  
  
 <span data-ttu-id="1e9c5-136"><xref:System.Resources>-Namespace</span><span class="sxs-lookup"><span data-stu-id="1e9c5-136"><xref:System.Resources> namespace</span></span>  
 <span data-ttu-id="1e9c5-137">Stellt Klassen zum Erstellen, Bearbeiten und Verwenden von Ressourcen bereit.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-137">Provides classes for creating, manipulating, and using resources.</span></span>  
  
 <span data-ttu-id="1e9c5-138"><xref:System.Text>-Namespace</span><span class="sxs-lookup"><span data-stu-id="1e9c5-138"><xref:System.Text> namespace</span></span>  
 <span data-ttu-id="1e9c5-139">Enthält Klassen, die die ASCII-, ANSI-, Unicode- und andere Zeichencodierungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-139">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>  
  
 [<span data-ttu-id="1e9c5-140">Resgen.exe (Resource File Generator)</span><span class="sxs-lookup"><span data-stu-id="1e9c5-140">Resgen.exe (Resource File Generator)</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 <span data-ttu-id="1e9c5-141">Beschreibt die Verwendung von Resgen.exe zur Konvertierung von TXT-Dateien und RESX-Dateien (XML-basiertes Ressourcenformat) in binäre RESOURCES-Dateien der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-141">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>  
  
 [<span data-ttu-id="1e9c5-142">Winres.exe (Windows Forms Resource Editor-Tool)</span><span class="sxs-lookup"><span data-stu-id="1e9c5-142">Winres.exe (Windows Forms Resource Editor)</span></span>](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 <span data-ttu-id="1e9c5-143">Beschreibt die Verwendung von Winres.exe zur Lokalisierung von Windows Forms-Formularen.</span><span class="sxs-lookup"><span data-stu-id="1e9c5-143">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>
