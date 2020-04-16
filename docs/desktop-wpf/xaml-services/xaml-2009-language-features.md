---
title: XAML 2009-Sprachfunktionen
ms.date: 03/30/2017
helpviewer_keywords:
- XAML 2009 [XAML Services]
- XAML [XAML Services], XAML 2009
ms.assetid: f6bb18d8-c86a-4549-8862-323e6b32a8dd
ms.openlocfilehash: e58e6757b88958bf8a3547c8a272c2e6298dcecb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432839"
---
# <a name="xaml-2009-language-features"></a>XAML 2009-Sprachfunktionen
XAML 2009 ist der Kurzbegriff für neue XAML-Sprachfunktionen, die die vorhandene XAML-Sprachspezifikation erweitern. XAML 2009 führt mehrere neue Richtlinien und Konstrukte ein. Dazu gehört die [x:Arguments-Richtlinie](xarguments-directive.md); [die x:FactoryMethod-Richtlinie](xfactorymethod-directive.md); [die x:Reference Markup Extension](xreference-markup-extension.md); [die x:TypeArguments-Richtlinie](xtypearguments-directive.md); und integrierte Typen für Common Language Primitives (z. B. `x:Char`).

## <a name="xaml-2009-support-in-wpf-and-visual-studio"></a>XAML 2009-Unterstützung in WPF und Visual Studio

In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für XAML, das nicht WPF-markupkompiliert ist. Markupkompilierte XAML und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.

Beachten Sie, dass vorhandene Techniken zum Laden von Loose XAML in WPF auch mögliche Sicherheits- und Zugriffseinschränkungen auf CLR-Typen und das Typsystem besitzen, die restriktiver als für markupkompilierte XAML sind. Weitere Informationen finden Sie unter [Sicherheit (WPF)](../../framework/wpf/security-wpf.md) oder [WPF-Sicherheitsstrategie – Plattformsicherheit](../../framework/wpf/wpf-security-strategy-platform-security.md).

XAML 2009 führt auch zusätzliche Funktionen ein, die entweder die vorherigen XAML 2006-Konstrukte oder die grundlegenden Markupformulare ändern.

### <a name="xkey-as-an-object-element"></a>x:Key als Objektelement

XAML 2009 kann `x:Key` als ein Objekt unterstützen (ein Eigenschaftenelement mit Objektelementwert), XAML 2006 unterstützt `x:Key` dagegen nur als Attribut. Weitere Informationen finden Sie im Abschnitt „XAML 2009“ von [x:Key Directive](xkey-directive.md).

### <a name="xmlns-on-property-elements"></a>Xmlns für Eigenschaftenelemente

XAML 2009 kann XAML-Namespacedefinitionen (Xmlns) für Eigenschaftenelemente unterstützen; XAML 2006 unterstützt nur Xmlns-Definitionen für Objektelemente.

### <a name="event-attributes"></a>Ereignisattribute

Für von Ereignissen unterstützte Attribute wird in XAML 2006 davon ausgegangen, dass die Markupkompilierung enthalten ist, und die Ereignisse werden zur Markupkompilierung gesendet. XAML 2009 unterstützt ein Markupformular, das einer Markuperweiterung ähnelt, die die Ereignisverknüpfung bis zur Laufzeitanalyse und dem Laden der XAML zurückstellt. Allerdings verwenden WPF-Anwendungen und XAML-Szenarien für WPF-UI in der Regel nicht diese Funktion. WPF und die XAML 2006-Implementierung verwenden für einen Großteil der Ereignisattributverarbeitung eine Kombination aus der Ereignishandlerverknüpfung für Routingereignisse definiert auf <xref:System.Windows.UIElement> -Ebene und dem Markupcompilerschritt. Der Markupcompiler führt auch eine Vorverarbeitung für alle Ereignisattribute in XAML aus, bei denen die Buildvorgänge deklarieren, dass der Markupcompiler verwendet wird.

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über XAML (WPF)](../fundamentals/xaml.md)
