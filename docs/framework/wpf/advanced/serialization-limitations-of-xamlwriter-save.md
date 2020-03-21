---
title: Serialisierungseinschränkungen für XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: 96e917898320fb5d49f4e7dfc27daa7750af9d41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174367"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Serialisierungseinschränkungen für XamlWriter.Save
Die <xref:System.Windows.Markup.XamlWriter.Save%2A> API kann verwendet werden, um [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] den [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Inhalt einer Anwendung als Datei zu serialisieren. Es gibt jedoch einige wichtige Einschränkungen darin, was genau serialisiert wird. Diese Einschränkungen und einige allgemeine Aspekte werden in diesem Thema dokumentiert.  

<a name="Run_Time__Not_Design_Time_Representation"></a>
## <a name="run-time-not-design-time-representation"></a>Laufzeit-, statt Entwurfszeitdarstellung  
 Die grundphilosophie dessen, was durch <xref:System.Windows.Markup.XamlWriter.Save%2A> einen Aufruf serialisiert wird, ist, dass das Ergebnis eine Darstellung des Objekts ist, das zur Laufzeit serialisiert wird. Viele Entwurfszeiteigenschaften der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Originaldatei sind möglicherweise bereits optimiert oder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] gehen verloren, wenn die als In-Memory-Objekte geladen wird, und werden beim Aufruf <xref:System.Windows.Markup.XamlWriter.Save%2A> zur Serialisierung nicht beibehalten. Das serialisierte Ergebnis ist eine effektive Darstellung der konstruierten logischen Struktur der Anwendung, aber nicht notwendigerweise der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], mit der es erstellt wurde. Diese Probleme machen es extrem <xref:System.Windows.Markup.XamlWriter.Save%2A> schwierig, die Serialisierung als Teil einer umfangreichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Konstruktionsoberfläche zu verwenden.  
  
<a name="Serialization_is_Self_Contained"></a>
## <a name="serialization-is-self-contained"></a>Die Serialisierung ist in sich geschlossen  
 Die serialisierte <xref:System.Windows.Markup.XamlWriter.Save%2A> Ausgabe von ist in sich geschlossen; Alles, was serialisiert wird, ist in einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] einzelnen Seite mit einem einzelnen Stammelement und keinen externen Verweisen außer URIs enthalten. Wenn Ihre Seite beispielsweise auf Ressourcen aus Anwendungsressourcen verweist, werden diese so angezeigt, als handele es sich um eine Komponente der serialisierten Seite.  
  
<a name="Extension_References_are_Dereferenced"></a>
## <a name="extension-references-are-dereferenced"></a>Erweiterungsverweise werden dereferenziert  
 Allgemeine Verweise auf Objekte durch verschiedene Markuperweiterungsformate, z.B. `StaticResource` oder `Binding`, werden durch den Serialisierungsprozess dereferenziert. Diese wurden bereits zu dem Zeitpunkt dereferenziert, als in-Memory-Objekte <xref:System.Windows.Markup.XamlWriter.Save%2A> von der Anwendungslaufzeit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellt wurden, und die Logik besucht das Original nicht erneut, um solche Verweise auf die serialisierte Ausgabe wiederherzustellen. Dadurch werden möglicherweise alle datengebundenen oder aus Ressourcen abgerufenen Werte auf den zuletzt zur Darstellung der Laufzeit verwendeten Wert gesperrt. Ein solcher Wert kann nur eingeschränkt oder indirekt von anderen lokal festgelegten Werten unterschieden werden. Bilder werden auch als Objektverweise auf Bilder serialisiert, wie sie im Projekt vorhanden sind, und nicht als ursprüngliche Quellreferenzen, wodurch der Dateiname oder URI verloren geht, auf den ursprünglich verwiesen wurde. Sogar Ressourcen, die auf der selben Seite deklariert werden, werden an den Punkt serialisiert, von dem aus auf sie verwiesen wird, und bleiben nicht als Schlüssel einer Ressourcenauflistung erhalten.  
  
<a name="Event_Handling_is_Not_Preserved"></a>
## <a name="event-handling-is-not-preserved"></a>Ereignisbehandlung wird nicht beibehalten  
 Wenn Ereignishandler, die durch [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzugefügt wurden, serialisiert werden, werden diese nicht beibehalten. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ohne CodeBehind (und auch ohne den zugehörigen x:Code-Mechanismus) kann keine prozedurale Logik zur Laufzeit serialisieren. Da die Serialisierung in sich geschlossen und auf die logische Struktur beschränkt ist, besteht keine Möglichkeit zur Speicherung der Ereignishandler. Folglich werden bei Ereignishandlerattributen sowohl das Attribut selbst als auch der Zeichenfolgenwert, der den Handler benennt, aus der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Ausgabe entfernt.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Realistische Szenarios für die Verwendung von XAMLWriter.Save  
 Obwohl die hier aufgeführten Einschränkungen recht umfangreich sind, <xref:System.Windows.Markup.XamlWriter.Save%2A> gibt es immer noch mehrere geeignete Szenarien für die Verwendung für die Serialisierung.  
  
- Vektorausgabe oder grafische Ausgabe: Die Ausgabe des gerenderten Bereichs kann dazu verwendet werden, den gleichen Vektor oder die gleichen Grafiken beim erneuten Laden zu reproduzieren.  
  
- Rich-Text und Flussdokumente: Text und alle darin enthaltenen Elementformatierungen und Elementeinschlüsse werden in der Ausgabe beibehalten. Dies kann für Mechanismen nützlich sein, die einer Zwischenablagefunktionalität ähneln.  
  
- Beibehalten von Geschäftsobjektdaten: Wenn Sie Daten in benutzerdefinierten Elementen wie XML-Daten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] gespeichert haben, solange Ihre Geschäftsobjekte grundlegenden Regeln folgen, wie z. B. die Bereitstellung benutzerdefinierter Konstruktoren und die Konvertierung für Nebeneigenschaftswerte, können diese Geschäftsobjekte durch Serialisierung verewigt werden.
