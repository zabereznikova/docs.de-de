---
title: Serialisierungseinschränkungen für XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: 5b9141d5df40d74c4682f418a8fb089fddcfcaa9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740744"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Serialisierungseinschränkungen für XamlWriter.Save
Die API-<xref:System.Windows.Markup.XamlWriter.Save%2A> kann verwendet werden, um den Inhalt einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung als [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei zu serialisieren. Es gibt jedoch einige wichtige Einschränkungen darin, was genau serialisiert wird. Diese Einschränkungen und einige allgemeine Aspekte werden in diesem Thema dokumentiert.  

<a name="Run_Time__Not_Design_Time_Representation"></a>   
## <a name="run-time-not-design-time-representation"></a>Laufzeit-, statt Entwurfszeitdarstellung  
 Die grundlegende Philosophie, die durch einen Aufruf von <xref:System.Windows.Markup.XamlWriter.Save%2A> serialisiert wird, besteht darin, dass das Ergebnis zur Laufzeit eine Darstellung des Objekts ist, das serialisiert wird. Viele Entwurfszeit Eigenschaften der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei werden möglicherweise bereits zu dem Zeitpunkt optimiert, zu dem die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als in-Memory-Objekte geladen werden, und werden nicht beibehalten, wenn Sie <xref:System.Windows.Markup.XamlWriter.Save%2A> zum Serialisieren aufruft. Das serialisierte Ergebnis ist eine effektive Darstellung der konstruierten logischen Struktur der Anwendung, aber nicht notwendigerweise der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], mit der es erstellt wurde. Diese Probleme erschweren die Verwendung der <xref:System.Windows.Markup.XamlWriter.Save%2A> Serialisierung als Teil einer umfassenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Entwurfs Oberfläche.  
  
<a name="Serialization_is_Self_Contained"></a>   
## <a name="serialization-is-self-contained"></a>Die Serialisierung ist in sich geschlossen  
 Die serialisierte Ausgabe von <xref:System.Windows.Markup.XamlWriter.Save%2A> ist eigenständig. alle Elemente, die serialisiert werden, sind in einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] einzelnen Seite, mit einem einzelnen Stamm Element und anderen externen verweisen als URIs enthalten. Wenn Ihre Seite beispielsweise auf Ressourcen aus Anwendungsressourcen verweist, werden diese so angezeigt, als handele es sich um eine Komponente der serialisierten Seite.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## <a name="extension-references-are-dereferenced"></a>Erweiterungsverweise werden dereferenziert  
 Allgemeine Verweise auf Objekte durch verschiedene Markuperweiterungsformate, z.B. `StaticResource` oder `Binding`, werden durch den Serialisierungsprozess dereferenziert. Diese wurden bereits zu dem Zeitpunkt dereferenziert, zu dem in-Memory-Objekte von der Anwendungs Laufzeit erstellt wurden, und die <xref:System.Windows.Markup.XamlWriter.Save%2A> Logik nimmt die ursprüngliche [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nicht erneut an, um solche Verweise auf die serialisierte Ausgabe wiederherzustellen. Dadurch werden möglicherweise alle datengebundenen oder aus Ressourcen abgerufenen Werte auf den zuletzt zur Darstellung der Laufzeit verwendeten Wert gesperrt. Ein solcher Wert kann nur eingeschränkt oder indirekt von anderen lokal festgelegten Werten unterschieden werden. Bilder werden auch als Objekt Verweise auf Bilder serialisiert, da Sie im Projekt vorhanden sind, und nicht als ursprüngliche Quell Verweise, wobei der Dateiname oder der URI, auf den ursprünglich verwiesen wurde, verloren gehen. Sogar Ressourcen, die auf der selben Seite deklariert werden, werden an den Punkt serialisiert, von dem aus auf sie verwiesen wird, und bleiben nicht als Schlüssel einer Ressourcenauflistung erhalten.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## <a name="event-handling-is-not-preserved"></a>Ereignisbehandlung wird nicht beibehalten  
 Wenn Ereignishandler, die durch [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzugefügt wurden, serialisiert werden, werden diese nicht beibehalten. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ohne CodeBehind (und auch ohne den zugehörigen x:Code-Mechanismus) kann keine prozedurale Logik zur Laufzeit serialisieren. Da die Serialisierung in sich geschlossen und auf die logische Struktur beschränkt ist, besteht keine Möglichkeit zur Speicherung der Ereignishandler. Folglich werden bei Ereignishandlerattributen sowohl das Attribut selbst als auch der Zeichenfolgenwert, der den Handler benennt, aus der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Ausgabe entfernt.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Realistische Szenarios für die Verwendung von XAMLWriter.Save  
 Obwohl die hier aufgeführten Einschränkungen recht umfangreich sind, gibt es noch einige geeignete Szenarien für die Verwendung von <xref:System.Windows.Markup.XamlWriter.Save%2A> für die Serialisierung.  
  
- Vektorausgabe oder grafische Ausgabe: Die Ausgabe des gerenderten Bereichs kann dazu verwendet werden, den gleichen Vektor oder die gleichen Grafiken beim erneuten Laden zu reproduzieren.  
  
- Rich-Text und Flussdokumente: Text und alle darin enthaltenen Elementformatierungen und Elementeinschlüsse werden in der Ausgabe beibehalten. Dies kann für Mechanismen nützlich sein, die einer Zwischenablagefunktionalität ähneln.  
  
- Beibehalten von Geschäftsobjekt Daten: Wenn Sie Daten in benutzerdefinierten Elementen (z. b. XML-Daten) gespeichert haben, sofern Ihre Geschäftsobjekte grundlegenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Regeln folgen, wie z. b. das Bereitstellen von benutzerdefinierten Konstruktoren und die Konvertierung für durch verweisende Eigenschaftswerte, Objekte können durch Serialisierung fortgeführt werden.
