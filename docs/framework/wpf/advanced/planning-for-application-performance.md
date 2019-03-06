---
title: Planen der Anwendungsleistung
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
ms.openlocfilehash: fda5330ff75c1744f3ed9d4394e51b5efb737071
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374426"
---
# <a name="planning-for-application-performance"></a>Planen der Anwendungsleistung
Der Erfolg Ihre Leistungsziele zu erreichen, hängt davon ab, wie gut Sie Ihre Leistungsstrategie für die entwickeln. Die Planung ist die erste Phase in ein Produkt entwickeln. Dieses Thema beschreibt einige sehr einfache Regeln für die Entwicklung einer Strategie für die gute Leistung.  
  
## <a name="think-in-terms-of-scenarios"></a>Stellen Sie sich im Hinblick auf Szenarien  
 Szenarien können Sie die wichtigen Komponenten Ihrer Anwendung konzentrieren. Szenarien werden in der Regel von Ihrem Kunden als auch Produkte von Wettbewerbern abgeleitet. Immer untersuchen Sie Ihre Kunden zu und herausfinden Sie, was wirklich sie begeistert, dass Ihr Produkt und Produkte von Wettbewerbern macht. Ihrer Kunden-Feedback können Sie primäre Szenario Ihrer Anwendung zu bestimmen. Wenn Sie eine Komponente entwerfen, die beim Start verwendet wird, ist es beispielsweise wahrscheinlich, dass die Komponente nur einmal aufgerufen wird, wenn die Anwendung wird gestartet. Dauer des verbindungsstarts wird zum Hauptszenario. Weitere Beispiele für wichtige Szenarien konnte die gewünschte Einzelbildrate für Animationssequenzen sein, oder die maximale Arbeitssatz für die Anwendung zugelassen werden.  
  
## <a name="define-goals"></a>Definieren von Zielen  
 Ziele können Sie bestimmen, ob eine Anwendung schneller oder langsamer ausgeführt wird. Sie sollten die Ziele für alle Szenarien definieren. Leistungsziele, die Sie definieren, sollten auf die Erwartungen Ihrer Kunden basieren. Es kann mit der Set-Leistung schwierig sein, die schon früh in der Anwendungsentwicklung Ziele durchlaufen weiterhin viele ungelösten Probleme vorliegen. Allerdings ist es besser, eine anfangsziel darin festgelegt, und bearbeiten Sie diese später als nicht auf alle haben ein Ziel.  
  
## <a name="understand-your-platform"></a>Verstehen Sie Ihre Plattform  
 Verwalten Sie immer den Zyklus der messen, überprüfen und während des Entwicklungszyklus der Anwendung optimieren/beheben. Von Anfang bis zum Ende des Entwicklungszyklus müssen Sie die Leistung Ihrer Anwendung in eine zuverlässige, stabile Umgebung messen. Vermeiden Sie die Variabilität durch externe Faktoren verursacht werden. Beim Testen der Leistung, sollten Sie z. B. Anti-Virus oder ein automatisches Update wie SMS zu deaktivieren, damit keine Leistungseinbußen Testergebnisse. Nachdem Sie die Leistung Ihrer Anwendung gemessen haben, müssen Sie die Änderungen zu identifizieren, die zu den wichtigsten Verbesserungen führen. Nachdem Sie Ihre Anwendung geändert haben, starten Sie den Zyklus erneut.  
  
## <a name="make-performance-tuning-an-iterative-process"></a>Stellen Sie einen iterativen Prozess die Optimierung der Leistung  
 Sie sollten die relative Kosten der einzelnen Funktionen kennen, die Sie verwenden möchten. Beispielsweise ist die Verwendung von Reflektion in Microsoft .NET Framework im Allgemeinen ressourcenintensiv in Bezug auf die Computerressourcen, damit Sie es mit Umsicht verwenden möchten. Dies bedeutet nicht die Verwendung von Reflektion zu vermeiden, nur, dass Sie achten sollten, die Erfüllung der leistungsanforderungen Ihrer Anwendung mit der leistungsanforderungen der Features abwägen, die Sie verwenden.  
  
## <a name="build-towards-graphical-richness"></a>Für Grafische Umfang erstellen  
 Eine wichtige Technik zum Erstellen eines skalierbaren Ansatzes bei der Verwirklichung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist die Leistung der Anwendung für die Erstellung für die grafische Vielfalt und Komplexität. Beginnen Sie immer mit den geringsten intensive leistungsressourcen zum Erreichen Ihrer Szenarioziele. Nachdem Sie diese Ziele erreichen, mithilfe von weitere intensive Leistungsfeatures, wobei immer Ihre Szenarioziele zu bedenken für grafische Vielfältigkeit erstellen. Beachten Sie, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist eine umfangreiche Plattform und sehr umfangreiche Grafikfeatures bereitstellt. Rechenintensive Funktionen ohne Sicherheitsaspekte zu berücksichtigen können sich negativ auf Ihre gesamtanwendung Leistung auswirken.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente sind durch die Funktionen für die umfassende Anpassung ihrer Darstellung, ohne ihr Steuerelementverhalten grundsätzlich erweiterbar. Nutzen von Stilen, Steuerelementvorlagen und Datenvorlagen, Sie erstellen und inkrementell entwickeln ein anpassbares [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , die passt sich an Ihren leistungsanforderungen.  
  
## <a name="see-also"></a>Siehe auch
- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
