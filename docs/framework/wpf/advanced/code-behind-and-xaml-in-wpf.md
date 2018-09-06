---
title: Code-Behind und XAML in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: ee08dc22588264b25d40b3fd818ef9ee1da90319
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032905"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-Behind und XAML in WPF
<a name="introduction"></a> CodeBehind ist ein Begriff zum Beschreiben des Codes, der mit Markup-definierten Objekten verknüpft ist, verwendet bei einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist Markupkompilierte. Dieses Thema beschreibt die Anforderungen für die Code-Behind sowie eine alternative Inline-Code-Mechanismus für den Code in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Erforderliche Komponenten](#Prerequisites)  
  
-   [Code-Behind und XAML-Sprache](#codebehind_and_the_xaml_language)  
  
-   [Code-Behind-Ereignishandler und Anforderungen der partiellen Klasse in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [X: Code](#x_Code)  
  
-   [Einschränkungen von Inlinecode](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie "Lesen" die [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) und einige grundlegende Kenntnisse über die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] und objektorientierten Programmierung.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Code-Behind und XAML-Sprache  
 Die XAML-Sprache enthält Features auf, die zum Zuordnen von Codedateien mit Markup-Dateien, auf der Seite der Markup-Datei ermöglichen. Genauer gesagt, die XAML-Sprache definiert die Sprachfunktionen [X: Class-Anweisung](../../../../docs/framework/xaml-services/x-class-directive.md), [X: Subclass-Anweisung](../../../../docs/framework/xaml-services/x-subclass-directive.md), und [X: ClassModifier-Anweisung](../../../../docs/framework/xaml-services/x-classmodifier-directive.md). Genau wie der Code erstellt werden muss und das Integrieren von Markup und Code, ist nicht Teil, was die XAML-Sprache angibt. Es bleibt bis zu Frameworks wie WPF, um zu bestimmen, wie Sie den Code integrieren, wie XAML in der Anwendung und Programmiermodelle und der Build mit Aktionen oder anderen unterstützen, die all dies ist erforderlich.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code-Behind-Ereignishandler und Anforderungen der partiellen Klasse in WPF  
  
-   Die partielle Klasse muss vom Typ abgeleitet werden, die das Stammelement sichert.  
  
-   Beachten Sie, dass es sich bei den Markup kompilieren Buildvorgängen Standardverhalten, Sie die Ableitung in der Definition der partiellen Klasse leer auf der Code-Behind-Seite lassen können. Das kompilierte Ergebnis wird die Seitenstamm Unterstützungstyp um als Grundlage für die partielle Klasse ist, werden wird davon ausgegangen, selbst wenn er nicht angegeben. Auf dieses Verhalten ist jedoch nicht empfohlen.  
  
-   Die Ereignishandler, die Sie im Code-Behind schreiben müssen Instanzmethoden sein und darf nicht statische Methoden sein. Diese Methoden müssen definiert werden, von der partiellen Klasse innerhalb der CLR-Namespace identifizierte `x:Class`. Sie können nicht qualifizieren Sie den Namen eines ereignishandlers um anzuweisen, ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor einen Ereignishandler für die ereignisverknüpfung in einer anderen Klassenbereich gesucht.  
  
-   Der Handler muss den Delegaten für das entsprechende Ereignis in das System von Unterstützungstypen übereinstimmen.  
  
-   Für die Microsoft Visual Basic-Sprache gesagt können Sie die sprachspezifischen `Handles` zuzuordnende Schlüsselwort Handler Instanzen und Ereignissen in der Handlerdeklaration anstatt durch Anfügen von Handlern, die mit Attributen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Diese Technik verfügt jedoch über einige Einschränkungen. da die `Handles` Schlüsselwort kann nicht unterstützt, die bestimmte Features von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignissystem, z. B. bestimmte Ereignisszenarien weitergeleitet oder angefügten Ereignisse. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>X: Code  
 [X: Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md) wird in einem-Anweisungselement definiert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Ein `x:Code` Richtlinie Element kann Inline-Programmcode enthalten. Der Code Inline definiert interagieren kann die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] auf derselben Seite. Das folgende Beispiel veranschaulicht die C#-Inlinecode. Beachten Sie, dass der Code innerhalb der `x:Code` -Element und der Code in gesetzt werden muss `<CDATA[`... `]]>` Inhalt mit Escapezeichen versehen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], sodass eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor (Interpretieren von entweder die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema oder die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schema) wird nicht versucht, zum Interpretieren des Inhalts buchstäblich wie [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Einschränkungen von Inlinecode  
 Sie sollten erwägen, zu vermeiden oder die Verwendung von Inline-Code einzuschränken. Im Hinblick auf die Architektur und die Codierung der Philosophie behält eine Trennung zwischen Markup und Code-Behind die Rollen-Designer und Entwickler viel klarer. Auf Weitere technische Ebene, der Code, den Sie für Inline-Code schreiben kann sein, schwierig zu erstellen, da Sie immer in schreiben die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] partielle Klasse generiert und können nur die standardzuordnungen von XML-Namespace verwenden. Da Sie keine hinzufügen können `using` -Anweisungen, müssen Sie vollständig qualifizieren vieler der [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] Aufrufe, die Sie vornehmen. Der Standardwert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Zuordnungen enthalten, die jedoch nicht alle [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Namespaces, die in vorhanden sind die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys müssen vollqualifiziert Aufrufe von Typen und Member in anderen CLR-Namespaces enthalten sind. Außerdem kann nicht definieren nichts über die partielle Klasse in den Inlinecode, und alle Benutzercodeentitäten, die Sie verweisen, als ein Element oder eine Variable in der generierten partiellen Klasse vorhanden sein. Andere Sprache Programmierfunktionen, z. B. Makros oder `#ifdef` für globale Variablen oder Buildvariablen, sind ebenfalls nicht verfügbar. Weitere Informationen finden Sie unter [X: Code-XAML-Grundtyp](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Systeminterner x:Code-XAML-Typ](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)  
 [Erstellen einer WPF-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Ausführliche Erläuterung der XAML-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
