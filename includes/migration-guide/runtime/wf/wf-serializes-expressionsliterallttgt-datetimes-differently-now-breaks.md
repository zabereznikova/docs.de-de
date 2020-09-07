---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496967"
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

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
