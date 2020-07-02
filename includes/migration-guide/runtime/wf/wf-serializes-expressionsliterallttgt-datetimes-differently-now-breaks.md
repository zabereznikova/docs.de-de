---
ms.openlocfilehash: 87013a04f7ff975e40a3c49c41c1c5acc2374066
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620412"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF serialisiert Expressions.Literal&lt;T&gt; DateTimes jetzt anders (unterbricht benutzerdefinierte XAML-Parser)

#### <a name="details"></a>Details

Das zugeordnete <xref:System.Windows.Markup.ValueSerializer>-Objekt konvertiert ein <xref:System.DateTime?displayProperty=fullName>- oder <xref:System.DateTimeOffset?displayProperty=fullName>-Objekt, dessen Second- und <xref:System.DateTime.Millisecond?displayProperty=fullName>-Komponenten (Sekunden und Millisekunden) ungleich 0 (null) sind und (für einen <xref:System.DateTime?displayProperty=fullName>-Wert) dessen <xref:System.DateTime.Kind>-Eigenschaft nicht angegeben ist, in eine Eigenschaftenelementsyntax anstatt in eine Zeichenfolge. Durch diese Änderung kann bei <xref:System.DateTime?displayProperty=fullName>- und <xref:System.DateTimeOffset?displayProperty=fullName>-Werten ein Roundtrip ausgeführt werden. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.

#### <a name="suggestion"></a>Vorschlag

Durch diese Änderung kann bei <xref:System.DateTime?displayProperty=fullName>- und <xref:System.DateTimeOffset?displayProperty=fullName>-Werten ein Roundtrip ausgeführt werden. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
