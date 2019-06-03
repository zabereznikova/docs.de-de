---
ms.openlocfilehash: 335647f899c79eff22e313fa40b2e2a73e7cfff0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379637"
---
### <a name="wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF serialisiert Expressions.Literal\<T> DateTimes jetzt anders (unterbricht benutzerdefinierte XAML-Parser)

|   |   |
|---|---|
|Details|Das zugeordnete <xref:System.Windows.Markup.ValueSerializer>-Objekt konvertiert ein <xref:System.DateTime?displayProperty=name>- oder <xref:System.DateTimeOffset?displayProperty=name>-Objekt, dessen Second- und <xref:System.DateTime.Millisecond?displayProperty=name>-Komponenten (Sekunden und Millisekunden) ungleich 0 (null) sind und (für einen <xref:System.DateTime?displayProperty=name>-Wert) dessen <xref:System.DateTime.Kind>-Eigenschaft nicht angegeben ist, in eine Eigenschaftenelementsyntax anstatt in eine Zeichenfolge. Durch diese Änderung kann bei <xref:System.DateTime?displayProperty=name>- und <xref:System.DateTimeOffset?displayProperty=name>-Werten ein Roundtrip ausgeführt werden. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.|
|Vorschlag|Durch diese Änderung kann bei <xref:System.DateTime?displayProperty=name>- und <xref:System.DateTimeOffset?displayProperty=name>-Werten ein Roundtrip ausgeführt werden. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
