---
title: "Code-Behind und XAML in WPF | Microsoft Docs"
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
  - "Code-Behind-Dateien, XAML"
  - "XAML, Code-Behind"
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Code-Behind und XAML in WPF
<a name="introduction"></a> "Code\-Behind" ist ein Ausdruck zum Beschreiben des Codes, der mit Markup\-definierten Objekten verknüpft ist, wenn für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite die Markupkompilierung ausgeführt wird.  In diesem Thema werden die Anforderungen für Code\-Behind und ein alternativer Inline\-Codemechanismus für Code in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beschrieben.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Vorbereitungsmaßnahmen](#Prerequisites)  
  
-   [Code\-Behind und die XAML\-Sprache](#codebehind_and_the_xaml_language)  
  
-   [Anforderungen von Code\-Behind, Ereignishandlern und partiellen Klassen in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [x:Code](#x_Code)  
  
-   [Inlinecodeeinschränkungen](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie die [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) gelesen haben und über Grundkenntnisse der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Programmierung und objektorientierten Programmierung verfügen.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## Code\-Behind und die XAML\-Sprache  
 Die XAML\-Sprache schließt Funktionen auf Sprachenebene ein, mit denen Codedateien von der Markupdateiseite mit Markupdateien verknüpft werden können.  Insbesondere definiert die XAML\-Sprache die Sprachfunktionen [x:Class\-Direktive](../../../../docs/framework/xaml-services/x-class-directive.md), [x:Subclass\-Direktive](../../../../docs/framework/xaml-services/x-subclass-directive.md) und [x:ClassModifier\-Direktive](../../../../docs/framework/xaml-services/x-classmodifier-directive.md).  Die genaue Angabe zur Erstellung des Codes und zur Integration von Markup und Code ist nicht Bestandteil der Angaben der XAML\-Sprache.  Es bleibt Frameworks wie z. B. WPF überlassen zu bestimmen, wie der Code integriert wird, wie XAML in der Anwendung und den Programmiermodellen verwendet wird. Ebenso übernehmen die Frameworks die Erstellungsvorgänge und sonstige Unterstützung, die dazu erforderlich ist.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## Anforderungen von Code\-Behind, Ereignishandlern und partiellen Klassen in WPF  
  
-   Die partielle Klasse muss von dem Typ abgeleitet werden, der das Stammelement unterstützt.  
  
-   Beachten Sie, dass Sie mit dem Standardverhalten der Erstellungsaktionen zur Markupkompilierung den Ableitungszwischenraum in der partiellen Klassendefinition auf der Code\-Behind\-Seite frei lassen können.  Das kompilierte Ergebnis geht davon aus, dass der Unterstützungstyp des Seitenstamms die Grundlage für die partielle Klasse bildet, auch wenn er nicht angegeben ist.  Sich auf dieses Verhalten zu verlassen ist jedoch keine optimale Methode.  
  
-   Die Ereignishandler, die Sie in den Code\-Behind schreiben, müssen Instanzmethoden sein und können keine statischen Methoden sein.  Diese Methoden müssen von der partiellen Klasse innerhalb des durch `x:Class` identifizierten CLR\-Namespace definiert werden.  Es ist nicht möglich, den Namen eines Ereignishandlers zu qualifizieren, um einen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor anzuweisen, in einem anderen Klassenbereich nach einem Ereignishandler für die Ereignisverknüpfung zu suchen.  
  
-   Der Handler muss mit dem Delegat für das entsprechende Ereignis im Unterstützungstypsystem übereinstimmen.  
  
-   Für die [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]\-Sprache können Sie das sprachspezifische Schlüsselwort `Handles` verwenden, um Instanzen und Ereignissen in der Handlerdeklaration Handler zuzuordnen, anstatt Handler in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attributen zuzuordnen.  Dieses Verfahren unterliegt jedoch einigen Einschränkungen, da das `Handles`\-Schlüsselwort nicht alle spezifischen Funktionen des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignissystems unterstützen kann, zum Beispiel bestimmte Szenarios mit Routingereignissen oder angefügten Ereignissen.  Ausführliche Informationen finden Sie unter [Visual Basic\- und WPF\-Ereignisbehandlung](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## x:Code  
 [x:Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md) ist ein in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definiertes Direktivenelement. Ein `x:Code`\-Direktivenelement kann Inlineprogrammierungscode enthalten.  Der Code, der inline definiert wird, kann mit dem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Code auf derselben Seite interagieren.  Das folgende Beispiel zeigt [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)]\-Inlinecode.  Beachten Sie, dass sich der Code innerhalb des `x:Code`\-Elements befindet und dass der Code in `<CDATA[`...`]]>` gesetzt sein muss, damit der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Inhalt mit Escapezeichen versehen wird und ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor \(der entweder das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Schema oder das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Schema interpretiert\) nicht versucht, den Inhalt wörtlich als [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] zu interpretieren.  
  
 [!code-xml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## Inlinecodeeinschränkungen  
 Sie sollten erwägen, die Verwendung von Inlinecode zu vermeiden oder einzuschränken.  Hinsichtlich der Architektur und des Codieransatzes bewirkt eine Trennung zwischen Markup und Code\-Behind, dass die Rollen des Designers und des Entwicklers klarer voneinander abgegrenzt sind.  Für die technische Ebene bedeutet dies, dass der Code, den Sie als Inlinecode schreiben, ggf. schwierig zu erstellen sein kann. Dies liegt daran, dass Sie immer in die generierte partielle Klasse der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] schreiben und dabei nur die standardmäßigen XML\-Namespacezuordnungen verwenden können.  Da Sie keine `using`\-Anweisungen hinzufügen können, müssen Sie viele der durchgeführten [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]\-Aufrufe vollständig qualifizieren.  Die standardmäßigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Zuordnungen enthalten die meisten [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Namespaces, die in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Assemblys vorhanden sind, jedoch nicht alle. Daher müssen Sie Aufrufe an Typen und Member in anderen CLR\-Namespaces vollständig qualifizieren.  Außerdem ist es nicht möglich, im Inlinecode mehr als die partielle Klasse zu definieren, und alle Benutzercodeentitäten, auf die Sie verweisen, müssen in der generierten partiellen Klasse als Member oder Variable vorhanden sein.  Andere sprachspezifische Programmierfunktionen, wie Makros oder `#ifdef` für globale Variablen oder Buildvariablen, stehen ebenfalls nicht zur Verfügung.  Weitere Informationen finden Sie unter [Systeminterner x:Code\-XAML\-Typ](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md).  
  
## Siehe auch  
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Systeminterner x:Code\-XAML\-Typ](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)   
 [Erstellen einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)