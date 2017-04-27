---
title: "Serialisierungseinschr&#228;nkungen f&#252;r XamlWriter.Save | Microsoft Docs"
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
  - "Einschränkungen für XamlWriter.Save"
  - "Serialisierungseinschränkungen für XamlWriter.Save"
  - "XamlWriter.Save, Serialisierungseinschränkungen für"
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Serialisierungseinschr&#228;nkungen f&#252;r XamlWriter.Save
[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A> kann verwendet werden, um den Inhalt einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendung als eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei zu serialisieren.  Im Hinblick darauf, was genau serialisiert wird, gibt es jedoch einige wichtige Einschränkungen.  Diese Einschränkungen und einige allgemeine Überlegungen werden in diesem Thema behandelt.  
  
   
  
<a name="Run_Time__Not_Design_Time_Representation"></a>   
## Laufzeit\- statt Entwurfszeitdarstellung  
 Die grundlegende Strategie dafür, was durch einen Aufruf an <xref:System.Windows.Markup.XamlWriter.Save%2A> serialisiert wird, ist, dass das Resultat eine Darstellung des serialisierten Objekts zur Laufzeit sein wird.  Viele Entwurfszeiteigenschaften der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei sind zu dem Zeitpunkt, zu dem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als Objekt im Arbeitsspeicher geladen wird, bereits optimiert oder verloren gegangen und werden nicht beibehalten, wenn Sie <xref:System.Windows.Markup.XamlWriter.Save%2A> zum Serialisieren aufrufen.  Das serialisierte Resultat ist eine effektive Darstellung der konstruierten logischen Struktur der Anwendung, aber nicht unbedingt der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], aus der es erzeugt wurde.  Aufgrund dieser Probleme ist es extrem schwierig, die <xref:System.Windows.Markup.XamlWriter.Save%2A>\-Serialisierung als Teil einer umfassenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Entwurfsoberfläche zu verwenden.  
  
<a name="Serialization_is_Self_Contained"></a>   
## Die Serialisierung ist in sich geschlossen  
 Die serialisierte Ausgabe von <xref:System.Windows.Markup.XamlWriter.Save%2A> ist in sich geschlossen. Alles, was serialisiert wird, ist in einer einzigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite enthalten, es gibt ein einziges Stammelement und keine externen Verweise außer [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].  Wenn Ihre Seite beispielsweise auf Ressourcen aus Anwendungsressourcen verweist, werden diese so angezeigt, als wären sie eine Komponente der Seite, die serialisiert wird.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## Erweiterungsverweise werden dereferenziert  
 Allgemeine Verweise auf Objekte in verschiedenen Markuperweiterungsformaten wie `StaticResource` oder `Binding` werden durch den Serialisierungsprozess dereferenziert.  Diese wurden bereits zu der Zeit dereferenziert, zu der Objekte im Arbeitsspeicher von der Laufzeitanwendung erstellt wurden, und die <xref:System.Windows.Markup.XamlWriter.Save%2A>\-Logik kehrt nicht zur ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zurück, um solche Verweise in der serialisierten Ausgabe wiederherzustellen.  Dies sperrt möglicherweise alle datengebundenen oder aus Ressourcen abgerufenen Werte auf die zuletzt von der Darstellung zur Laufzeit verwendeten Werte, wobei es nur eingeschränkt oder indirekt möglich ist, einen solchen Wert von anderen lokal festgelegten Werten zu unterscheiden.  Bilder werden auch als Objektverweise auf Bilder serialisiert, da sie im Projekt statt in den ursprünglichen Quellverweisen enthalten sind, wobei der Dateiname oder [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] verloren geht, auf den ursprünglich verwiesen wurde.  Selbst Ressourcen, die auf derselben Seite deklariert werden, werden in den Punkt serialisiert, von dem aus auf sie verwiesen wurde, statt als Schlüssel einer Ressourcenauflistung erhalten zu bleiben.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## Ereignisbehandlung wird nicht beibehalten  
 Wenn durch [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzugefügte Ereignishandler serialisiert werden, werden sie nicht beibehalten.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ohne Code\-Behind \(und auch ohne den zugehörigen x:Code\-Mechanismus\) kann prozedurale Logik zur Laufzeit nicht serialisieren.  Da Serialisierung in sich geschlossen und auf die logische Struktur beschränkt ist, gibt es keine Möglichkeit zur Speicherung der Eventhandler.  Folglich werden Eventhandlerattribute, sowohl das Attribut selbst als auch der Zeichenfolgenwert, der den Handler benennt, aus der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Ausgabe entfernt.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## Realistische Szenarien für die Verwendung von XAMLWriter.Save  
 Obwohl die hier aufgeführten Einschränkungen beträchtlich sind, gibt es doch mehrere Szenarien, in denen <xref:System.Windows.Markup.XamlWriter.Save%2A> für die Serialisierung geeignet ist.  
  
-   Vektorausgabe oder grafische Ausgabe: Die Ausgabe des gerenderten Bereichs kann verwendet werden, um beim erneuten Laden den gleichen Vektor oder die gleichen Grafiken zu reproduzieren.  
  
-   Rich\-Text\- und Flussdokumente: Text und jegliche darin enthaltene Elementformatierung sowie Elementkapselung wird in der Ausgabe beibehalten.  Dies kann für Mechanismen nützlich sein, die einer Zwischenablagefunktionalität ähneln.  
  
-   Erhalten von Daten für Geschäftsobjekte: Wenn Sie Daten in benutzerdefinierten Elementen speichern, beispielsweise [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten, können diese Geschäftsobjekte durch Serialisierung beibehalten werden. Dies setzt voraus, dass bei den Geschäftsobjekten grundlegende [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Regeln befolgt werden, beispielsweise das Bereitstellen von benutzerdefinierten Konstruktoren und das Konvertieren für durch Verweis übergebene Eigenschaftswerte.