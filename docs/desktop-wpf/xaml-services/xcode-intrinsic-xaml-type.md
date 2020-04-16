---
title: Systeminterner x:Code-XAML-Typ
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432803"
---
# <a name="xcode-intrinsic-xaml-type"></a>Systeminterner x:Code-XAML-Typ
Ermöglicht die Platzierung von Code in einer XAML-Produktion. Dieser Code kann entweder von jeder XAML-Prozessorimplementierung kompiliert werden, die XAML kompiliert, oder in der XAML-Produktion für spätere Verwendungen, z. B. Interpretation durch eine Laufzeit, belassen werden.

## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a>Bemerkungen

Der Code `x:Code` innerhalb des XAML-Direktivierungselements wird weiterhin im allgemeinen XML-Namespace und in den bereitgestellten XAML-Namespaces interpretiert. Daher ist es in der Regel notwendig, den Code, der für `x:Code` ein `CDATA` Segment verwendet wird, einzuschließen.

`x:Code`ist nicht für alle möglichen Bereitstellungsmechanismen einer XAML-Produktion zulässig. In bestimmten Frameworks (z. B. WPF) muss der Code kompiliert werden. In anderen Frameworks ist die `x:Code` Verwendung im Allgemeinen nicht zulässig.

Bei Frameworks, `x:Code` die verwalteten Inhalt zulassen, `x:Code` wird der richtige Sprachcompiler für Den Inhalt durch Einstellungen und Ziele des enthaltenden Projekts bestimmt, das zum Kompilieren der Anwendung verwendet wird.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Code, `x:Code` der für WPF deklariert wurde, weist mehrere bemerkenswerte Einschränkungen auf:

- Das `x:Code` Direktivenelement muss ein sofortiges untergeordnetes Element des Stammelements der XAML-Produktion sein.

- [x:Klassendirektive](xclass-directive.md) muss für das übergeordnete Stammelement bereitgestellt werden.

- Der darin `x:Code` platzierte Code wird durch Kompilierung behandelt, um innerhalb des Bereichs der partiellen Klasse zu liegen, die bereits für diese XAML-Seite erstellt wird. Daher muss der gesamte Code, den Sie definieren, Member oder Variablen dieser partiellen Klasse sein.

- Sie können keine zusätzlichen Klassen definieren, außer durch Verschachteln einer Klasse innerhalb der partiellen Klasse (Verschachtelung ist zulässig, aber sie ist nicht typisch, da geschachtelte Klassen in XAML nicht referenziert werden können). CLR-Namespaces, die nicht der Namespace sind, der für die vorhandene Partipartklasse verwendet wird, können nicht definiert oder hinzugefügt werden.

- Verweise auf Codeentitäten außerhalb des CLR-Namespace der Teilklasse müssen alle vollständig qualifiziert sein. Wenn Member deklariert werden, die überschrieben werden, müssen die überschreibbaren Member der Partipartklasse mit dem sprachspezifischen Überschreibungsschlüsselwort angegeben werden. Wenn Member, `x:Code` die im Gültigkeitsbereich deklariert wurden, mit Membern der partiellen Klasse in Konflikt stehen, die aus dem XAML erstellt wurden, so dass der Compiler den Konflikt meldet, kann die XAML-Datei nicht kompiliert oder geladen werden.

## <a name="see-also"></a>Weitere Informationen

- [x:Class-Direktive](xclass-directive.md)
- [Code-Behind und XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Übersicht über XAML (WPF)](../fundamentals/xaml.md)
