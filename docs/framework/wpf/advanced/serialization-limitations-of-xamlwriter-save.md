---
title: Serialisierungseinschränkungen für XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: cbe8d517b8794f6aae7190457a077422d235acb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Serialisierungseinschränkungen für XamlWriter.Save
Die [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A> können verwendet werden, um den Inhalt der Serialisieren einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] -Anwendung als ein [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei. Es gibt jedoch einige wichtige Einschränkungen darin, was genau serialisiert wird. Diese Einschränkungen und einige allgemeine Aspekte werden in diesem Thema dokumentiert.  
  
 
  
<a name="Run_Time__Not_Design_Time_Representation"></a>   
## <a name="run-time-not-design-time-representation"></a>Laufzeit-, statt Entwurfszeitdarstellung  
 Objekte, die durch einen Aufruf von serialisiert ist die grundlegende Philosophie <xref:System.Windows.Markup.XamlWriter.Save%2A> ist, dass das Ergebnis eine Darstellung des Objekts, das serialisiert wird, zur Laufzeit. Viele Entwurfszeiteigenschaften des ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei ist möglicherweise bereits optimiert oder verloren geht, indem die Zeit, die die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als Objekte im Arbeitsspeicher geladen wird, und werden nicht beibehalten, wenn Sie aufrufen <xref:System.Windows.Markup.XamlWriter.Save%2A> zu serialisieren. Das serialisierte Ergebnis ist eine effektive Darstellung der konstruierten logischen Struktur der Anwendung, aber nicht notwendigerweise der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], mit der es erstellt wurde. Diese Probleme ist es extrem schwierig, mithilfe der <xref:System.Windows.Markup.XamlWriter.Save%2A> Serialisierung als Teil einer umfassenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Entwurfsoberfläche angezeigt.  
  
<a name="Serialization_is_Self_Contained"></a>   
## <a name="serialization-is-self-contained"></a>Die Serialisierung ist in sich geschlossen  
 Die serialisierte Ausgabe von <xref:System.Windows.Markup.XamlWriter.Save%2A> eigenständig; alles, was serialisiert wird, der in enthalten ist ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Einzelseite, mit der ein einzelnes Stammelement und keine externen Verweise außer [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]. Wenn Ihre Seite beispielsweise auf Ressourcen aus Anwendungsressourcen verweist, werden diese so angezeigt, als handele es sich um eine Komponente der serialisierten Seite.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## <a name="extension-references-are-dereferenced"></a>Erweiterungsverweise werden dereferenziert  
 Allgemeine Verweise auf Objekte durch verschiedene Markuperweiterungsformate, z.B. `StaticResource` oder `Binding`, werden durch den Serialisierungsprozess dereferenziert. Diese wurden bereits dereferenziert, zu dem Zeitpunkt, die Objekte im Arbeitsspeicher von der Anwendungslaufzeit erstellt wurden und die <xref:System.Windows.Markup.XamlWriter.Save%2A> Logik ist nicht mehr die ursprünglichen überarbeitet [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] um solche Verweise auf die serialisierte Ausgabe wiederherzustellen. Dadurch werden möglicherweise alle datengebundenen oder aus Ressourcen abgerufenen Werte auf den zuletzt zur Darstellung der Laufzeit verwendeten Wert gesperrt. Ein solcher Wert kann nur eingeschränkt oder indirekt von anderen lokal festgelegten Werten unterschieden werden. Bilder werden ebenfalls als Objektverweise auf Bilder serialisiert, da sie im Projekt und nicht als ursprüngliche Quellenverweise enthalten sind. Dabei verlieren sie den Dateinamen oder die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], auf die ursprünglich verwiesen wurde. Sogar Ressourcen, die auf der selben Seite deklariert werden, werden an den Punkt serialisiert, von dem aus auf sie verwiesen wird, und bleiben nicht als Schlüssel einer Ressourcenauflistung erhalten.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## <a name="event-handling-is-not-preserved"></a>Ereignisbehandlung wird nicht beibehalten  
 Wenn Ereignishandler, die durch [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzugefügt wurden, serialisiert werden, werden diese nicht beibehalten. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ohne CodeBehind (und auch ohne den zugehörigen x:Code-Mechanismus) kann keine prozedurale Logik zur Laufzeit serialisieren. Da die Serialisierung in sich geschlossen und auf die logische Struktur beschränkt ist, besteht keine Möglichkeit zur Speicherung der Ereignishandler. Folglich werden bei Ereignishandlerattributen sowohl das Attribut selbst als auch der Zeichenfolgenwert, der den Handler benennt, aus der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Ausgabe entfernt.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Realistische Szenarios für die Verwendung von XAMLWriter.Save  
 Während die Einschränkungen aufgeführt. hier sind relativ erhebliche, es sind noch mehrere geeignete Szenarien für die Verwendung von <xref:System.Windows.Markup.XamlWriter.Save%2A> für die Serialisierung.  
  
-   Vektorausgabe oder grafische Ausgabe: Die Ausgabe des gerenderten Bereichs kann dazu verwendet werden, den gleichen Vektor oder die gleichen Grafiken beim erneuten Laden zu reproduzieren.  
  
-   Rich-Text und Flussdokumente: Text und alle darin enthaltenen Elementformatierungen und Elementeinschlüsse werden in der Ausgabe beibehalten. Dies kann für Mechanismen nützlich sein, die einer Zwischenablagefunktionalität ähneln.  
  
-   Erhalten von Daten für Geschäftsobjekte: Wenn Sie Daten in benutzerdefinierten Elementen wie z.B. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten gespeichert haben, können diese Geschäftsobjekte durch Serialisierung beibehalten werden. Voraussetzung hierfür ist, dass bei den Geschäftsobjekten grundlegende [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Regeln befolgt werden, wie z.B. das Bereitstellen von benutzerdefinierten Konstruktoren und das Konvertieren für durch Verweis übergebene Eigenschaftswerte.
