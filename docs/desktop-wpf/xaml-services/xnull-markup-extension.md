---
title: x:Null-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432695"
---
# <a name="xnull-markup-extension"></a>x:Null-Markuperweiterung

Gibt `null` als Wert für ein XAML-Element an.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>Bemerkungen

Das Schlüsselwort für einen Nullverweis in C- und C++ ist null. Das Microsoft Visual Basic-Schlüsselwort `Nothing`für einen `{x:Null}` Nullverweis ist , sie verwenden jedoch immer als XAML-Verwendung, unabhängig davon, welche CodeBehind-Sprache Sie dem XAML zuordnen.

Die `x:Null` Markuperweiterung hat keine festsetzbaren Eigenschaften.

Eine Nullverwendung ist häufig mit der XAML-Member-Exposition eines CLR-Werts <xref:System.Nullable%601> verknüpft.

Die `x:Null` Markuperweiterung verwendet, wie alle XAML-Markuperweiterungen, die geschweiften Klammern (`{,}`), um der Verarbeitung von Attributwerten zu entgehen, die nicht als Literale oder Ereignishandlerverweise gelten. Attributsyntax ist die Syntax, die am häufigsten mit dieser Markuperweiterung verwendet wird. Eine Objektelementsyntax `<x:Null />` ist technisch möglich, wird `x:Null` aber nur selten verwendet, da die Markuperweiterung keine Positionsparameter oder Konstruktionsargumente aufweist.

Informationen zu Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

In .NET XAML Services wird die Verarbeitung für <xref:System.Windows.Markup.NullExtension> diese Markuperweiterung durch die Klasse definiert.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Beachten `null` Sie, dass dies nicht unbedingt der anfängliche Nichtsetwert für eine Abhängigkeitseigenschaft des Referenztyps ist. Der anfängliche Standardwert kann für jede Abhängigkeitseigenschaft variieren und auf eigenschaftsspezifischen Metadaten basieren. Viele Abhängigkeitseigenschaften `null` akzeptieren aufgrund ihrer Validierungsrückrufimplementierungen weder durch Markup noch über Code einen Wert. Weitere Informationen zu Abhängigkeitseigenschaften finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../framework/wpf/advanced/dependency-properties-overview.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Übersicht über XAML (WPF)](../fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
