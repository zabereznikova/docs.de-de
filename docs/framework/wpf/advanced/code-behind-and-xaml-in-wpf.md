---
title: Code-Behind und XAML in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 09d4f010ca53c5e3d2d9dede172e7ae2102261b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541547"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-Behind und XAML in WPF
<a name="introduction"></a> Code-Behind-ist ein Begriff Beschreiben des Codes, der mit Markup-definierten Objekten verknüpft ist, wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist Markupkompilierte. In diesem Thema wird beschrieben, Anforderungen für die Code-Behind sowie einen alternativen Inline-Code-Mechanismus, um Code in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Erforderliche Komponenten](#Prerequisites)  
  
-   [Code-Behind und die XAML-Sprache](#codebehind_and_the_xaml_language)  
  
-   [Code-Behind, Ereignishandler und Teilklasse Anforderungen in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [X: Code](#x_Code)  
  
-   [Inlinecode Einschränkungen](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie "Lesen" die [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) und haben einige grundlegende Kenntnisse der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] und objektorientierte Programmierung.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Code-Behind und die XAML-Sprache  
 Die XAML-Sprache enthält Sprachebene Barrierefreiheitsfunktionen es möglich, Markupdateien aus der Datei-Markupdateiseite Codedateien zuzuordnen. Genauer gesagt, die XAML-Sprache definiert die Sprachfunktionen [X: Class-Direktive](../../../../docs/framework/xaml-services/x-class-directive.md), [X: Subclass-Direktive](../../../../docs/framework/xaml-services/x-subclass-directive.md), und [X: ClassModifier-Direktive](../../../../docs/framework/xaml-services/x-classmodifier-directive.md). Genau wie der Code erzeugt werden soll, sowie zum Integrieren von Markup und Code, ist nicht Teil, was die Verwendung von XAML-Sprache angibt. Es bleibt bis zu Frameworks wie z. B. WPF, bestimmen, wie die Integration des Codes, wie zur Verwendung von XAML in der Anwendung und Programmiermodelle, und der Build Aktionen oder andere unterstützen, die dies erfordert.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code-Behind, Ereignishandler und Teilklasse Anforderungen in WPF  
  
-   Die partielle Klasse muss vom Typ abgeleitet werden, die das Stammelement sichert.  
  
-   Beachten Sie, dass es sich bei den Markup kompilieren Buildvorgängen Standardverhalten, Sie die Ableitung in der partiellen Klassendefinition auf der Code-Behind-Seite weglassen können. Kompilierte Ergebnis wird die Seitenstamm-Unterstützungstyp als Grundlage für die partielle Klasse wird davon ausgegangen, selbst wenn er nicht angegeben. Vertrauensstellungen der vertrauenden Seite auf dieses Verhalten ist jedoch nicht empfohlen.  
  
-   Die Ereignishandler, die Sie im Code-behind schreiben müssen Instanzmethoden sein und darf nicht statische Methoden sein. Diese Methoden müssen definiert werden, von der partiellen Klasse innerhalb der CLR-Namespace identifiziert durch `x:Class`. Der Name eines ereignishandlers anweisen kann nicht qualifiziert werden eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor für einen Ereignishandler für die ereignisverknüpfung im Gültigkeitsbereich einer anderen Klasse gesucht werden soll.  
  
-   Der Handler muss der Delegat für das entsprechende Ereignis Unterstützungstypsystem entsprechen.  
  
-   Für die Microsoft Visual Basic-Sprache insbesondere können Sie die sprachspezifischen `Handles` zuzuordnende Schlüsselwort Handler Instanzen und Ereignissen in der Handlerdeklaration anstatt durch Anfügen von Handlern mit Attributen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Allerdings muss diese Technik einige Einschränkungen verfügen, da die `Handles` Schlüsselwort nicht unterstützt, der die bestimmten Funktionen des die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignissystem, z. B. bestimmte Ereignisszenarien weitergeleitet oder angefügte Ereignisse. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>X: Code  
 [X: Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md) ist in einem Anweisungselement definiert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Ein `x:Code` Richtlinie Element kann Inline-Programmcode enthalten. Der Code Inline definiert interagieren kann die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] auf derselben Seite. Das folgende Beispiel veranschaulicht die C#-Inlinecode. Beachten Sie, dass der Code innerhalb der `x:Code` -Element, sodass der Code eingeschlossen werden muss `<CDATA[`... `]]>` als Escapesequenz für den Inhalt für [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], sodass eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor (entweder die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema oder die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schema) wird nicht versuchen, Interpretieren des Inhalts buchstäblich als [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Inlinecode Einschränkungen  
 Sie sollten vermeiden oder die Verwendung von Inlinecode einzuschränken. Hinsichtlich der Architektur und Philosophie Codierung behält eine Trennung zwischen Markup und CodeBehind die Rollen-Designer und Entwickler weitaus distinct. Auf einer Ebene technischere Codes, den Sie für Inlinecode zu schreiben kann noch komplexer werden zu schreiben, da Sie immer in Schreiben der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] partielle Klasse generiert und können nur die standardzuordnungen von XML-Namespace verwenden. Da Sie hinzufügen können `using` -Anweisungen, müssen Sie vollständig qualifizieren Großteil der [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] Aufrufe, die Sie vornehmen. Die Standardeinstellung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Zuordnungen enthalten, die meisten jedoch nicht alle [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Namespaces, die im vorhanden sind die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys aus; müssen vollqualifiziert Aufrufe von Typen und Member in anderen CLR-Namespaces enthalten sind. Auch keine definieren alles jenseits der partiellen Klasse im Inlinecode, und alle Code benutzerentitäten, die Sie verweisen, als ein Element oder eine Variable in der generierten partiellen Klasse vorhanden sein. Andere sprachspezifische Programmierfunktionen, z. B. Makros oder `#ifdef` für globalen Variablen oder Variablen erstellen, sind ebenfalls nicht verfügbar. Weitere Informationen finden Sie unter [X: Code-XAML-Grundtyps](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Systeminterner x:Code-XAML-Typ](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)  
 [Erstellen einer WPF-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Ausführliche Erläuterung der XAML-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
