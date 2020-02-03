---
title: Code Behind und XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 212a37fb7fbcb7e66a669d96671333be793956df
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738095"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-Behind und XAML in WPF
<a name="introduction"></a>Code Behind ist ein Begriff, der verwendet wird, um den Code zu beschreiben, der mit Markup definierten Objekten verknüpft ist, wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite Markup kompiliert wird. In diesem Thema werden die Anforderungen für Code Behind und ein alternativer Inline Code Mechanismus für Code in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]beschrieben.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Voraussetzungen](#Prerequisites)  
  
- [Code Behind und XAML-Sprache](#codebehind_and_the_xaml_language)  
  
- [Code Behind, Ereignis Handler und partielle Klassen Anforderungen in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Code](#x_Code)  
  
- [Einschränkungen für Inline Code](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Voraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie die [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) gelesen haben und über grundlegende Kenntnisse der CLR-und objektorientierten Programmierung verfügen.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Code Behind und XAML-Sprache  
 Die XAML-Sprache umfasst Funktionen auf Sprachebene, die es ermöglichen, Code Dateien aus der Markup Datei Seite mit Markup Dateien zu verknüpfen. Die XAML-Sprache definiert insbesondere die Sprachfunktionen [x:Class Directive](../../../desktop-wpf/xaml-services/xclass-directive.md), [x:Subclass Directive](../../../desktop-wpf/xaml-services/xsubclass-directive.md)und [x:ClassModifier-Direktive](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md). Wie der Code erstellt werden sollte und wie Markup und Code integriert werden, ist nicht Teil der von der XAML-Sprache festgelegten Sprache. Es bleibt an Frameworks wie WPF, um zu bestimmen, wie der Code integriert werden soll, wie XAML in den Anwendungs-und Programmier Modellen verwendet wird, und welche Buildaktionen oder andere Unterstützung benötigt werden.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code Behind, Ereignis Handler und partielle Klassen Anforderungen in WPF  
  
- Die partielle Klasse muss von dem Typ abgeleitet werden, der das Stamm Element unterstützt.  
  
- Beachten Sie, dass Sie unter dem Standardverhalten der Build-Aktionen für die Markup Kompilierung die Ableitung in der partiellen Klassendefinition auf der Code-Behind-Seite leer lassen können. Das kompilierte Ergebnis geht davon aus, dass der Unterstützungstyp des Seiten Stamms die Grundlage für die partielle Klasse ist, auch wenn er nicht angegeben ist. Es ist jedoch nicht empfehlenswert, dieses Verhalten zu nutzen.  
  
- Die Ereignishandler, die Sie im Code-Behind schreiben, müssen Instanzmethoden sein und können keine statischen Methoden sein. Diese Methoden müssen von der partiellen Klasse innerhalb des CLR-Namespace definiert werden, der durch `x:Class`identifiziert wird. Sie können den Namen eines Ereignis Handlers nicht so qualifizieren, dass er einen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor anweist, nach einem Ereignishandler für die Ereignis Verkabelung in einem anderen Klassen Bereich zu suchen.  
  
- Der Handler muss mit dem Delegaten für das entsprechende Ereignis im Unterstützungs Typsystem identisch sein.  
  
- Speziell für die Microsoft Visual Basic-Sprache können Sie das sprachspezifische `Handles`-Schlüsselwort verwenden, um Handler Instanzen und Ereignissen in der Handlerdeklaration zuzuordnen, anstatt Handler mit Attributen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]anzufügen. Dieses Verfahren weist jedoch einige Einschränkungen auf, da das `Handles`-Schlüsselwort nicht alle spezifischen Funktionen des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignis Systems unterstützen kann, z. b. bestimmte Routing Ereignis Szenarios oder angefügte Ereignisse. Weitere Informationen finden Sie unter [Visual Basic-und WPF-Ereignis Behandlung](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x:Code  
 [x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md) ist ein Direktivenelement, das in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert ist. Ein `x:Code` Direktivenelement kann Inline Programmierungs Code enthalten. Der Inline definierte Code kann mit dem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] auf derselben Seite interagieren. Im folgenden Beispiel wird Inline C# Code veranschaulicht. Beachten Sie, dass sich der Code innerhalb des `x:Code`-Elements befindet und dass der Code von `<CDATA[`...`]]>` eingeschlossen werden muss, um den Inhalt für XML mit Escapezeichen zu versehen, sodass ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor (der entweder das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema oder das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schema interpretiert) nicht versucht, den Inhalt buchstäblich als XML zu interpretieren.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Einschränkungen für Inline Code  
 Sie sollten in Erwägung gezogen werden, die Verwendung von Inline Code zu vermeiden oder einzuschränken. Im Hinblick auf Architektur-und Codierungs Philosophie sorgt die Beibehaltung einer Trennung zwischen Markup und Code-Behind dafür, dass Designer-und Entwickler Rollen erheblich unterschieden werden. Auf einer komplexeren Ebene kann der Code, den Sie für Inline Code schreiben, umständlich zum Schreiben sein, da Sie immer in die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] generierte partielle Klasse schreiben und nur die Standard Zuordnungen für XML-Namespaces verwenden können. Da Sie keine `using`-Anweisungen hinzufügen können, müssen Sie viele der API-Aufrufe, die Sie vornehmen, vollständig qualifizieren. Die standardmäßigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Zuordnungen umfassen die meisten, aber nicht alle CLR-Namespaces, die in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Assemblys vorhanden sind. Sie müssen die Aufrufe von Typen und Membern vollständig qualifizieren, die in den anderen CLR-Namespaces enthalten sind. Sie können auch nichts außerhalb der partiellen Klasse im Inline Code definieren, und alle Benutzercode Entitäten, auf die Sie verweisen, müssen als Member oder Variable innerhalb der generierten partiellen Klasse vorhanden sein. Andere sprachspezifische Programmierfunktionen, z. b. Makros oder `#ifdef` für globale Variablen oder Buildvariablen, sind ebenfalls nicht verfügbar. Weitere Informationen finden Sie unter [x:Code-System interner XAML-Typ](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Systeminterner x:Code-XAML-Typ](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [Erstellen einer WPF-Anwendung](../app-development/building-a-wpf-application-wpf.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
