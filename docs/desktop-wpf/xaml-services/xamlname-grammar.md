---
title: XamlName-Grammatik
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 2fc74990b15caaa9b58e6eea5b0212ea22505674
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433049"
---
# <a name="xamlname-grammar"></a>XamlName-Grammatik

XamlName Grammar ist eine bestimmte Grammatik, die in der XAML-Sprachspezifikation [MS-XAML] definiert ist, die hier aus Gründen der Benutzerfreundlichkeit wiedergegeben wird.

## <a name="from-the-xaml-specification"></a>Aus der XAML-Spezifikation

Die [MS-XAML]-Spezifikation definiert die Grammatik XamlName, um den Satz von rechtlichen symbolischen Bezeichnern zu identifizieren, die für Typen und Eigenschaften verwendet werden.

Zeichenfolgenwerte vom Typ XamlName müssen der folgenden Grammatik entsprechen:

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

Dies setzt die folgenden allgemeinen Kategoriewerte voraus, wie in der Unicode-Zeichendatenbank definiert

| Unicode-Kategorie   | BESCHREIBUNG                   |
|--------------------|-------------------------------|
| Lu                 | Letter, Uppercase (Buchstabe, Großschreibung)             |
| Ll                 | Letter, Lowercase (Buchstabe, Kleinschreibung)             |
| Lt                 | Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)             |
| Lm                 | Letter, Modifier (Buchstabe, Modifizierer)              |
| Lo                 | Letter, Other (Buchstabe, andere)                 |
| Mn                 | Mark, Nicht-Abstand             |
| Mc                 | Mark, Spacing Combining (Satzzeichen, Kombinationszeichen mit Vorschub)       |
| Nd                 | Zahl, Dezimal               |
| Nl                 | Number, Letter (Zahl, Buchstabe)                |

XAML definiert eine zweite Grammatik, DottedXamlName, die für Eigenschaften- und ereignisqualifizierte Verweise sowie für angefügte Member verwendet wird. Weitere Informationen finden <xref:System.Windows.DependencyProperty> Sie unter [und XAML-Übersicht (WPF)](../fundamentals/xaml.md).

Zeichenfolgenwerte vom Typ DottedXamlName müssen der folgenden Grammatik entsprechen:

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>Bemerkungen

Die vollständige Spezifikation finden Sie unter [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).
