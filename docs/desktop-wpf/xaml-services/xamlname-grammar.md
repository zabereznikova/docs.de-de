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
ms.openlocfilehash: ceb027938b6d4313babbe02949e0b6dd5ee85589
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556693"
---
# <a name="xamlname-grammar"></a>XamlName-Grammatik

Die XamlName-Grammatik ist eine bestimmte Grammatik, die in der XAML-Sprachspezifikation [MS-XAML] definiert ist, die zur einfacheren Wiedergabe hier reproduziert wird.

## <a name="from-the-xaml-specification"></a>Aus der XAML-Spezifikation

Die [MS-XAML]-Spezifikation definiert den Grammatik-XamlName, um den Satz von juristischen symbolischen bezeichmern zu identifizieren, die für Typen und Eigenschaften verwendet werden.

Zeichen folgen Werte vom Typ XamlName müssen der folgenden Grammatik entsprechen:

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

Dabei werden die folgenden allgemeinen Kategoriewerte angenommen, wie in der Unicode-Zeichen Datenbank definiert.

| Unicode-Kategorie   | BESCHREIBUNG                   |
|--------------------|-------------------------------|
| Lu                 | Letter, Uppercase (Buchstabe, Großschreibung)             |
| Ll                 | Letter, Lowercase (Buchstabe, Kleinschreibung)             |
| Lt                 | Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)             |
| Lm                 | Letter, Modifier (Buchstabe, Modifizierer)              |
| Lo                 | Letter, Other (Buchstabe, andere)                 |
| Mn                 | Markierung, nicht Abstand             |
| Mc                 | Mark, Spacing Combining (Satzzeichen, Kombinationszeichen mit Vorschub)       |
| Nd                 | Zahl, Decimal               |
| Nl                 | Number, Letter (Zahl, Buchstabe)                |

XAML definiert eine zweite Grammatik (DottedXamlName), die für Eigenschafts-und Ereignis qualifizierte Verweise und auch für angefügte Member verwendet wird. Weitere Informationen finden Sie unter <xref:System.Windows.DependencyProperty> und [Übersicht über XAML (WPF)](../fundamentals/xaml.md).

Zeichen folgen Werte vom Typ "DottedXamlName" müssen der folgenden Grammatik entsprechen:

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>Hinweise

Die vollständige Spezifikation finden Sie unter [ \[ MS-XAML \] ](/previous-versions/msp-n-p/ff650760(v=pandp.10)).
