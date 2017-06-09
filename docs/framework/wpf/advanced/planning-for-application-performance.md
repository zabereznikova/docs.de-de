---
title: "Planen der Anwendungsleistung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungen, Optimieren"
  - "WPF-Anwendung, Optimieren"
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Planen der Anwendungsleistung
Das erfolgreiche Erreichen der Leistungsziele hängt davon ab, wie gut Sie die Leistungsstrategie entwickeln.  Planung stellt bei jedem Projekt die erste Phase der Entwicklung dar.  In diesem Thema werden einige sehr einfache Regeln für die Entwicklung einer guten Leistungsstrategie beschrieben.  
  
## Berücksichtigen von Szenarien  
 Mithilfe von Szenarien können Sie sich auf die wichtigen Komponenten der Anwendungen konzentrieren.  Szenarien werden in der Regel von Ihren Kunden oder von Konkurrenzprodukten abgeleitet.  Beobachten Sie immer Ihre Kunden, und finden Sie heraus, was genau sie an Ihren und an den Produkten der Konkurrenz schätzen.  Mithilfe des Feedbacks der Kunden können Sie das primäre Szenario der Anwendung bestimmen.  Wenn Sie z. B. eine Komponente entwerfen, die beim Starten verwendet wird, ist es sehr wahrscheinlich, dass sie nur einmal, nämlich beim Starten der Anwendung, aufgerufen wird.  Die Startzeit wird zum Hauptszenario.  Andere Hauptszenarien könnten die gewünschte Framerate für Animationssequenzen oder das für die Anwendung maximal zulässige Workingset umfassen.  
  
## Definieren von Zielen  
 Mithilfe von Zielen können Sie bestimmten, ob eine Anwendung schneller oder langsamer ausgeführt wird.  Definieren Sie Ziele für alle Szenarien.  Alle definierten Leistungsziele sollten auf den Erwartungen der Kunden basieren.  Das Festlegen von Leistungszielen zu einem frühen Zeitpunkt im Entwicklungszyklus einer Anwendung kann sich als schwierig erweisen, da es noch viele ungelöste Probleme gibt.  Es ist jedoch besser, sich zu Beginn ein Ziel zu setzen und es später zu ändern, als ohne Ziel zu arbeiten.  
  
## Verstehen der Plattform  
 Behalten Sie während des Entwicklungszyklus der Anwendung immer den Zyklus von Messen, Überprüfen und Verfeinern\/Korrigieren bei.  Sie müssen während des gesamten Entwicklungszyklus die Leistung der Anwendung in einer zuverlässigen und stabilen Umgebung messen.  Vermeiden Sie durch externe Faktoren verursachte Variabilität.  Deaktivieren Sie beim Testen der Leistung beispielsweise Antivirenprogramme oder automatische Updates wie SMS, damit die Ergebnisse des Leistungstests nicht beeinträchtigt werden.  Nachdem Sie die Leistung der Anwendung gemessen haben, müssen Sie die Änderungen identifizieren, mit denen sich die größte Leistungssteigerung erzielen lässt.  Sobald Sie die Anwendung geändert haben, starten Sie den Zyklus erneut.  
  
## Leistungsoptimierung als iterativer Prozess  
 Sie sollten die relativen Kosten für jedes Feature kennen, das Sie verwenden.  Beispielsweise ist die Verwendung der Reflektion in [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] in der Regel sehr ressourcenintensiv und sollte daher mit Bedacht verwendet werden.  Dies bedeutet nicht, dass die Reflektion nicht verwendet werden soll. Sie sollten jedoch darauf achten, ein Gleichgewicht zwischen den Leistungsanforderungen der Anwendung und den Leistungsanforderungen der verwendeten Features zu finden.  
  
## Erstellen unter Berücksichtigung vielfältiger Grafikmöglichkeiten  
 Eine wichtige Technik beim Erstellen eines skalierbaren Ansatzes zum Erreichen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungsleistung besteht darin, bei der Erstellung vielfältige und komplexe Grafikmöglichkeiten zu berücksichtigen.  Beginnen Sie immer mit den am wenigsten ressourcenintensiven Features, um die Szenarioziele zu erreichen.  Sobald Sie diese Ziele erreicht haben, können Sie ressourcenintensivere Features verwenden, um vielfältige Grafikmöglichkeiten zu berücksichtigen. Denken Sie dabei immer an Ihre Szenarioziele.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist eine äußerst vielfältige Plattform, die äußerst vielfältige Grafikfeatures bereitstellt.  Das gedankenlose Verwenden ressourcenintensiver Features kann sich negativ auf die Gesamtleistung der Anwendung auswirken.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente sind grundsätzlich erweiterbar, da sie eine umfassende Anpassung ihrer Darstellung zulassen, ohne ihr Verhalten als Steuerelement zu ändern.  Indem Sie die Vorteile von Stilen, Datenvorlagen und Steuerelementvorlagen nutzen, können Sie eine anpassbare [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] erstellen bzw. schrittweise entwickeln, die sich Ihren Leistungsanforderungen anpasst.  
  
## Siehe auch  
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Nutzen der Vorteile der Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Projektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)