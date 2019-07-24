---
title: Code-Behind und XAML in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: acd8c9ff0a4ff718dba272958a3e63820bcf1354
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401609"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-Behind und XAML in WPF
<a name="introduction"></a>Code Behind ist ein Begriff, der verwendet wird, um den Code zu beschreiben, der mit Markup definierten Objekten verknüpft [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist, wenn eine Seite Markup kompiliert wird. In diesem Thema werden die Anforderungen für Code Behind und ein alternativer Inline Code Mechanismus für Code in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]beschrieben.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Erforderliche Komponenten](#Prerequisites)  
  
- [Code Behind und XAML-Sprache](#codebehind_and_the_xaml_language)  
  
- [Code Behind, Ereignis Handler und partielle Klassen Anforderungen in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Code](#x_Code)  
  
- [Einschränkungen für Inline Code](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie die [Übersicht über XAML (WPF)](xaml-overview-wpf.md) gelesen haben und über grundlegende Kenntnisse der CLR-und objektorientierten Programmierung verfügen.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Code Behind und XAML-Sprache  
 Die XAML-Sprache umfasst Funktionen auf Sprachebene, die es ermöglichen, Code Dateien aus der Markup Datei Seite mit Markup Dateien zu verknüpfen. Die XAML-Sprache definiert insbesondere die Sprachfunktionen [x:Class Directive](../../xaml-services/x-class-directive.md), [x:Subclass Directive](../../xaml-services/x-subclass-directive.md)und [x:ClassModifier-Direktive](../../xaml-services/x-classmodifier-directive.md). Wie der Code erstellt werden sollte und wie Markup und Code integriert werden, ist nicht Teil der von der XAML-Sprache festgelegten Sprache. Es bleibt an Frameworks wie WPF, um zu bestimmen, wie der Code integriert werden soll, wie XAML in den Anwendungs-und Programmier Modellen verwendet wird, und welche Buildaktionen oder andere Unterstützung benötigt werden.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code Behind, Ereignis Handler und partielle Klassen Anforderungen in WPF  
  
- Die partielle Klasse muss von dem Typ abgeleitet werden, der das Stamm Element unterstützt.  
  
- Beachten Sie, dass Sie unter dem Standardverhalten der Build-Aktionen für die Markup Kompilierung die Ableitung in der partiellen Klassendefinition auf der Code-Behind-Seite leer lassen können. Das kompilierte Ergebnis geht davon aus, dass der Unterstützungstyp des Seiten Stamms die Grundlage für die partielle Klasse ist, auch wenn er nicht angegeben ist. Es ist jedoch nicht empfehlenswert, dieses Verhalten zu nutzen.  
  
- Die Ereignishandler, die Sie im Code-Behind schreiben, müssen Instanzmethoden sein und können keine statischen Methoden sein. Diese Methoden müssen von der partiellen Klasse innerhalb des CLR-Namespace definiert werden `x:Class`, der durch identifiziert wird. Sie können den Namen eines Ereignis Handlers nicht so qualifizieren, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dass er einen Prozessor anweist, nach einem Ereignishandler für die Ereignis Verkabelung in einem anderen Klassen Bereich zu suchen.  
  
- Der Handler muss mit dem Delegaten für das entsprechende Ereignis im Unterstützungs Typsystem identisch sein.  
  
- Speziell für die Microsoft Visual Basic-Sprache können Sie das sprachspezifische `Handles` Schlüsselwort verwenden, um Handler-Instanzen und-Ereignissen in der Handlerdeklaration zuzuordnen, anstatt Handler mit Attributen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]anzufügen. Dieses Verfahren weist jedoch einige Einschränkungen `Handles` [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf, da das-Schlüsselwort nicht alle spezifischen Funktionen des Ereignis Systems unterstützen kann, z. b. bestimmte Routing Ereignis Szenarios oder angefügte Ereignisse. Weitere Informationen finden Sie unter [Visual Basic-und WPF-Ereignis Behandlung](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x:Code  
 [x:Code](../../xaml-services/x-code-intrinsic-xaml-type.md) ist ein Direktivenelement [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], das in definiert ist. Ein `x:Code` Direktivenelement kann Inline Programmierungs Code enthalten. Der Inline definierte Code kann mit dem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] auf derselben Seite interagieren. Im folgenden Beispiel wird Inline C# Code veranschaulicht. Beachten Sie, dass sich der Code `x:Code` innerhalb des-Elements befindet und dass der Code `<CDATA[`umgeben sein muss... [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], um den Inhalt für [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]zu verwenden, damit ein Prozessor (interpretiert entweder das Schema oder das Schema) nicht versucht, den Inhalt buchstäblich als zu interpretieren. `]]>`  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Einschränkungen für Inline Code  
 Sie sollten in Erwägung gezogen werden, die Verwendung von Inline Code zu vermeiden oder einzuschränken. Im Hinblick auf Architektur-und Codierungs Philosophie sorgt die Beibehaltung einer Trennung zwischen Markup und Code-Behind dafür, dass Designer-und Entwickler Rollen erheblich unterschieden werden. Auf einer komplexeren Ebene kann der Code, den Sie für Inline Code schreiben, umständlich zum Schreiben sein, da Sie immer in die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] generierte partielle Klasse schreiben und nur die standardmäßigen XML-Namespace Zuordnungen verwenden können. Da Sie keine- `using` Anweisungen hinzufügen können, müssen Sie viele der API-Aufrufe, die Sie vornehmen, vollständig qualifizieren. Die Standard [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Zuordnungen umfassen die meisten, aber nicht alle CLR-Namespaces, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in den Assemblys vorhanden sind. Sie müssen die Aufrufe von Typen und Membern, die in den anderen CLR-Namespaces enthalten sind, vollständig qualifizieren. Sie können auch nichts außerhalb der partiellen Klasse im Inline Code definieren, und alle Benutzercode Entitäten, auf die Sie verweisen, müssen als Member oder Variable innerhalb der generierten partiellen Klasse vorhanden sein. Andere sprachspezifische Programmierfunktionen, wie z. b `#ifdef` . Makros oder globale Variablen oder Buildvariablen, sind ebenfalls nicht verfügbar. Weitere Informationen finden Sie unter [x:Code-System interner XAML-Typ](../../xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Systeminterner x:Code-XAML-Typ](../../xaml-services/x-code-intrinsic-xaml-type.md)
- [Erstellen einer WPF-Anwendung](../app-development/building-a-wpf-application-wpf.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
