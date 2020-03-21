---
title: Code-Behind und XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 32283d5b81bf92999a97711ded13a8b533ae3028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145344"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-Behind und XAML in WPF
<a name="introduction"></a>Code-Behind ist ein Begriff, der verwendet wird, um den Code [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zu beschreiben, der mit Markup-definierten Objekten verbunden ist, wenn eine Seite markupkompiliert wird. In diesem Thema werden die Anforderungen an CodeBehind sowie ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]alternativer Inlinecodemechanismus für Code in beschrieben.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Voraussetzungen](#Prerequisites)  
  
- [Code-Behind und die XAML-Sprache](#codebehind_and_the_xaml_language)  
  
- [Code-Behind-, Ereignishandler- und Partial Class-Anforderungen in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Code](#x_Code)  
  
- [Inline-Codeeinschränkungen](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie die [XAML-Übersicht (WPF)](../../../desktop-wpf/fundamentals/xaml.md) gelesen haben und über einige Grundkenntnisse der CLR und der objektorientierten Programmierung verfügen.  
  
<a name="codebehind_and_the_xaml_language"></a>
## <a name="code-behind-and-the-xaml-language"></a>Code-Behind und die XAML-Sprache  
 Die XAML-Sprache enthält Funktionen auf Sprachebene, die es ermöglichen, Codedateien von der Markupdateiseite aus Codedateien mit Markupdateien zu verknüpfen. Insbesondere definiert die XAML-Sprache die Sprachmerkmale [x:Class-Direktive](../../../desktop-wpf/xaml-services/xclass-directive.md), [x:Unterklassenrichtlinie](../../../desktop-wpf/xaml-services/xsubclass-directive.md)und [x:ClassModifier-Richtlinie](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md). Wie genau der Code erstellt werden soll und wie Markup und Code integriert werden, ist nicht Teil dessen, was die XAML-Sprache angibt. Es bleibt Frameworks wie WPF überlassen, um zu bestimmen, wie der Code integriert wird, wie XAML in die Anwendungs- und Programmiermodelle verwendet wird und welche Buildaktionen oder andere Unterstützung dies alles erfordert.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code-Behind-, Ereignishandler- und Partial Class-Anforderungen in WPF  
  
- Die partielle Klasse muss von dem Typ abgeleitet werden, der das Root-Element unterstützt.  
  
- Beachten Sie, dass Sie unter dem Standardverhalten der Markupkompilierungsaufbauaktionen die Ableitung in der partiellen Klassendefinition auf der CodeBehind-Seite leer lassen können. Das kompilierte Ergebnis geht davon aus, dass der Sicherungstyp des Seitenstamms die Grundlage für die partielle Klasse ist, auch wenn er nicht angegeben wurde. Es ist jedoch keine bewährte Methode, sich auf dieses Verhalten zu verlassen.  
  
- Die Ereignishandler, die Sie in den CodeBehind schreiben, müssen Instanzmethoden sein und dürfen keine statischen Methoden sein. Diese Methoden müssen durch die partielle Klasse innerhalb `x:Class`des CLR-Namespace definiert werden, der durch identifiziert wird. Sie können den Namen eines Ereignishandlers [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nicht qualifizieren, um einen Prozessor anzuweisen, nach einem Ereignishandler für die Ereignisverdrahtung in einem anderen Klassenbereich zu suchen.  
  
- Der Handler muss mit dem Delegaten für das entsprechende Ereignis im Sicherungstypsystem übereinstimmen.  
  
- Speziell für die Microsoft Visual Basic-Sprache können `Handles` Sie das sprachspezifische Schlüsselwort verwenden, um Handler mit Instanzen und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Ereignissen in der Handlerdeklaration zu verknüpfen, anstatt Handler mit Attributen in anzufügen. Diese Technik weist jedoch einige `Handles` Einschränkungen auf, da das Schlüsselwort nicht alle spezifischen Features des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignissystems unterstützen kann, z. B. bestimmte routingierte Ereignisszenarien oder angefügte Ereignisse. Weitere Informationen finden Sie unter [Visual Basic und WPF Event Handling](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>
## <a name="xcode"></a>x:Code  
 [x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md) ist ein Direktivenelement, das in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert ist. Ein `x:Code` Direktivenelement kann Inline-Programmiercode enthalten. Der code, der inline definiert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist, kann mit dem auf derselben Seite interagieren. Im folgenden Beispiel wird der Inline-Code von C-Code veranschaulicht. Beachten Sie, dass `x:Code` sich der Code innerhalb des `<CDATA[`Elements befindet und dass der Code von ... `]]>` , um den Inhalt für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] XML zu entkommen, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sodass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Prozessor (entweder das Schema oder das Schema interpretiert) nicht versucht, den Inhalt wörtlich als XML zu interpretieren.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>
## <a name="inline-code-limitations"></a>Inline-Codeeinschränkungen  
 Sie sollten die Verwendung von Inlinecode vermeiden oder einschränken. In Bezug auf Architektur und Codierungsphilosophie wird die Trennung zwischen Markup und Code-Behind durch die Aufrechterhaltung einer Trennung zwischen Markup und Code-Behind die Designer- und Entwicklerrollen viel deutlicher. Auf einer eher technischen Ebene kann der Code, den Sie für Inlinecode schreiben, umständlich zu schreiben sein, da Sie immer in die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] generierte Teilklasse schreiben und nur die standardmäßigen XML-Namespacezuordnungen verwenden können. Da Sie `using` keine Anweisungen hinzufügen können, müssen Sie viele der von Ihnen tätigen API-Aufrufe vollständig qualifizieren. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Standardzuordnungen enthalten die meisten, aber nicht alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] CLR-Namespaces, die in den Assemblys vorhanden sind. Sie müssen Aufrufe von Typen und Membern, die in den anderen CLR-Namespaces enthalten sind, vollständig qualifizieren. Sie können auch nichts über die partielle Klasse im Inlinecode hinaus definieren, und alle Benutzercodeentitäten, auf die Sie verweisen, müssen als Member oder Variable innerhalb der generierten Partiellenklasse vorhanden sein. Andere sprachspezifische Programmierfunktionen, z. `#ifdef` B. Makros oder gegen globale Variablen oder Buildvariablen, sind ebenfalls nicht verfügbar. Weitere Informationen finden Sie unter [x:Code Intrinsic XAML Type](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Systeminterner x:Code-XAML-Typ](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [Erstellen einer WPF-Anwendung](../app-development/building-a-wpf-application-wpf.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
