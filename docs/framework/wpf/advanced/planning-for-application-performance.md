---
title: Planen der Anwendungsleistung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f47f56e28064c852e5d8f721bdb3a0f73172c12a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="planning-for-application-performance"></a>Planen der Anwendungsleistung
Der Erfolg der Leistungsziele zu erreichen, hängt davon ab, wie gut Ihre Leistungsstrategie entwickeln. Die Planung ist die erste Phase in einem Produkt zu entwickeln. Dieses Thema beschreibt einige sehr einfache Regeln für das Entwickeln einer Strategie für die gute Leistung.  
  
## <a name="think-in-terms-of-scenarios"></a>Berücksichtigen von Szenarien  
 Szenarien können Sie wichtige Komponente Ihrer Anwendung konzentrieren. Szenarien werden in der Regel aus Ihrer Kunden sowie Konkurrenzprodukten abgeleitet. Immer untersuchen Sie Ihre Kunden zu und herauszufinden Sie, was tatsächlich diese Ihres Produkts und Ihrer Mitbewerber Produkte begeistert macht. Ihrer Kunden-Feedback können Sie Ihre primäre Anwendungsszenario zu bestimmen. Für die Instanz, wenn Sie eine Komponente entwerfen, die beim Start verwendet wird, ist es wahrscheinlich, dass die Komponente nur einmal aufgerufen wird, wenn die Anwendung wird gestartet. Die Startzeit wird die Hauptszenario. Weitere Beispiele für wichtige Szenarien konnte die gewünschte Framerate für Animationssequenzen werden oder die maximaler Arbeitssatz, die für die Anwendung zulässig.  
  
## <a name="define-goals"></a>Definieren von Zielen  
 Ziele können Sie bestimmen, ob eine Anwendung schneller oder langsamer ausgeführt wird. Sie sollten für alle Szenarien Ziele definieren. Alle Leistungsziele, die Sie definieren sollte auf die kundenerwartungen basieren. Es kann schwierig zu Satz Leistung sein, die Ziele in einer frühen Phase der Anwendungsentwicklung durchlaufen, wenn es noch viele ungelösten Probleme vorliegen sind. Allerdings ist es besser, eine anfängliche Ziel festgelegt, und Überarbeiten es später als nicht auf alle haben ein Ziel.  
  
## <a name="understand-your-platform"></a>Verstehen der Plattform  
 Behalten Sie immer den Zyklus messen, untersuchen, während der Anwendungsentwicklungszyklus optimieren/korrigieren. Vom Anfang bis zum Ende des Entwicklungszyklus müssen Sie die Leistung Ihrer Anwendung in eine zuverlässige und stabile Umgebung messen. Vermeiden Sie die Variabilität durch externe Faktoren verursacht. Beim Testen der Leistung sollten Sie z. B. Deaktivieren von Antiviren- oder automatische Updates wie SMS, damit keine Leistungseinbußen Testergebnisse. Nachdem Sie die Leistung Ihrer Anwendung gemessen haben, müssen Sie die Änderungen zu identifizieren, die die größte Leistungssteigerung führt. Nachdem Sie Ihre Anwendung geändert haben, starten Sie den Zyklus erneut.  
  
## <a name="make-performance-tuning-an-iterative-process"></a>Stellen Sie einen iterativen Prozess für die Leistungsoptimierung  
 Sie sollten die relative Kosten der einzelnen Funktionen kennen, die Sie verwenden möchten. Beispielsweise die Verwendung von Reflektion im [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] ist im Allgemeinen Leistung rechenintensiven im Hinblick auf die Computerressourcen, daher würden mit Bedacht verwendet werden sollen. Dies bedeutet nicht die Verwendung von Reflektion zu vermeiden, nur, dass Sie darauf achten, die Erfüllung der leistungsanforderungen Ihrer Anwendung mit den Anforderungen der Leistung der Funktionen zu verteilen, die Sie verwenden werden soll.  
  
## <a name="build-towards-graphical-richness"></a>Grafische Reichhaltigkeit ergeben  
 Eine wichtige Verfahren zum Erstellen eines skalierbaren Ansatzes für das erreichen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Leistung der Anwendung ist das grafische Umfang und Komplexität zu erstellen. Beginnen Sie immer mit der geringsten rechenintensiven leistungsressourcen um zu Ihrem Szenarioziele zu erreichen. Nachdem Sie diese Ziele erreichen, mithilfe von weitere rechenintensiven Leistungsfunktionen, beachten Sie Ihre Szenarioziele Beibehaltung für Grafik Reichhaltigkeit erstellen. Beachten Sie, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist eine sehr umfangreiche Plattform und sehr umfangreiche Grafikfeatures bereitstellt. Mit rechenintensiven Leistungsfunktionen ohne nachzudenken kann die gesamtleistung der Anwendungsleistung negativ beeinträchtigt werden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente sind grundsätzlich erweiterbar werden umfassende Anpassung ihrer Darstellung, ihr Steuerelementverhalten nicht ändern können. Durch die Nutzung von Formatvorlagen, Datenvorlagen und Steuerelementvorlagen, können Sie erstellen und inkrementell weiterentwickelt ein anpassbares [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , die passt sich an Ihren leistungsanforderungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Optimieren der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Vorteile der Hardware nutzen](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Objektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
