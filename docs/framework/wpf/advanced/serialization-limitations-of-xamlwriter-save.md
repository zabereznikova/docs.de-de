---
title: Serialisierungseinschränkungen für XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: 89cb36dba63dccdf7e52b7fcafbe3d9fc2fea1e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113281"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Serialisierungseinschränkungen für XamlWriter.Save
Die [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A> können verwendet werden, um den Inhalt der serialisieren eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] -Anwendung als eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei. Es gibt jedoch einige wichtige Einschränkungen darin, was genau serialisiert wird. Diese Einschränkungen und einige allgemeine Aspekte werden in diesem Thema dokumentiert.  

<a name="Run_Time__Not_Design_Time_Representation"></a>   
## <a name="run-time-not-design-time-representation"></a>Laufzeit-, statt Entwurfszeitdarstellung  
 Die grundlegende Strategie dafür, was durch einen Aufruf von serialisiert wird <xref:System.Windows.Markup.XamlWriter.Save%2A> besteht darin, dass das Resultat eine Darstellung des Objekts, das serialisiert wird, zur Laufzeit sein wird. Viele Entwurfszeiteigenschaften der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei ist möglicherweise bereits optimiert oder verloren geht, mit der Zeit, die die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als Objekte im Arbeitsspeicher geladen wird, und werden nicht beibehalten, wenn Sie aufrufen <xref:System.Windows.Markup.XamlWriter.Save%2A> serialisiert. Das serialisierte Ergebnis ist eine effektive Darstellung der konstruierten logischen Struktur der Anwendung, aber nicht notwendigerweise der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], mit der es erstellt wurde. Diese Probleme machen es extrem schwierig, verwenden Sie die <xref:System.Windows.Markup.XamlWriter.Save%2A> Serialisierung als Teil einer umfassenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Entwurfsoberfläche.  
  
<a name="Serialization_is_Self_Contained"></a>   
## <a name="serialization-is-self-contained"></a>Die Serialisierung ist in sich geschlossen  
 Die serialisierte Ausgabe von <xref:System.Windows.Markup.XamlWriter.Save%2A> ist in sich geschlossen; alles, was serialisiert wird, der in enthalten ist ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] einzelne Seite, mit der ein einzelnes Stammelement und keinen externen Verweise außer [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]. Wenn Ihre Seite beispielsweise auf Ressourcen aus Anwendungsressourcen verweist, werden diese so angezeigt, als handele es sich um eine Komponente der serialisierten Seite.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## <a name="extension-references-are-dereferenced"></a>Erweiterungsverweise werden dereferenziert  
 Allgemeine Verweise auf Objekte durch verschiedene Markuperweiterungsformate, z.B. `StaticResource` oder `Binding`, werden durch den Serialisierungsprozess dereferenziert. Diese wurden bereits zu dem Zeitpunkt dereferenziert, die in-Memory-Objekte durch die Anwendungslaufzeit erstellt wurden und die <xref:System.Windows.Markup.XamlWriter.Save%2A> -Logik kehrt nicht mehr den ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] um solche Verweise auf die serialisierte Ausgabe wiederherzustellen. Dadurch werden möglicherweise alle datengebundenen oder aus Ressourcen abgerufenen Werte auf den zuletzt zur Darstellung der Laufzeit verwendeten Wert gesperrt. Ein solcher Wert kann nur eingeschränkt oder indirekt von anderen lokal festgelegten Werten unterschieden werden. Bilder werden ebenfalls als Objektverweise auf Bilder serialisiert, da sie im Projekt und nicht als ursprüngliche Quellenverweise enthalten sind. Dabei verlieren sie den Dateinamen oder die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], auf die ursprünglich verwiesen wurde. Sogar Ressourcen, die auf der selben Seite deklariert werden, werden an den Punkt serialisiert, von dem aus auf sie verwiesen wird, und bleiben nicht als Schlüssel einer Ressourcenauflistung erhalten.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## <a name="event-handling-is-not-preserved"></a>Ereignisbehandlung wird nicht beibehalten  
 Wenn Ereignishandler, die durch [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzugefügt wurden, serialisiert werden, werden diese nicht beibehalten. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ohne CodeBehind (und auch ohne den zugehörigen X: Code-Mechanismus) kann keine prozedurale Logik zur Laufzeit serialisieren. Da die Serialisierung in sich geschlossen und auf die logische Struktur beschränkt ist, besteht keine Möglichkeit zur Speicherung der Ereignishandler. Folglich werden bei Ereignishandlerattributen sowohl das Attribut selbst als auch der Zeichenfolgenwert, der den Handler benennt, aus der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Ausgabe entfernt.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Realistische Szenarios für die Verwendung von XAMLWriter.Save  
 Während die Einschränkungen aufgeführt. hier sind ziemlich umfangreich, es gibt noch mehrere geeignete Szenarien für die Verwendung <xref:System.Windows.Markup.XamlWriter.Save%2A> für die Serialisierung.  
  
-   Vektorausgabe oder grafische Ausgabe: Die Ausgabe des gerenderten Bereichs kann dazu verwendet werden, den gleichen Vektor oder Grafiken beim erneuten Laden zu reproduzieren.  
  
-   Rich Text und Flussdokumente Dokumente: Text und alle Element elementformatierungen und elementeinschlüsse darin wird in der Ausgabe beibehalten. Dies kann für Mechanismen nützlich sein, die einer Zwischenablagefunktionalität ähneln.  
  
-   Beibehalten von Daten für Geschäftsobjekte: Wenn Sie Daten in benutzerdefinierten Elementen wie z. B. gespeichert haben [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten, solange Ihre Geschäftsobjekte grundlegende folgen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Regeln wie das Bereitstellen von benutzerdefinierten Konstruktoren und das Konvertieren für durch Verweis Eigenschaftswerte, die diese Geschäftsobjekte werden können über die Serialisierung aufrechterhalten.
