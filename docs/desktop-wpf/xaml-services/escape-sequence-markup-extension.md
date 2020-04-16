---
title: '{}Escape Sequence - Markup-Erweiterung'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432965"
---
# <a name="-escape-sequence--markup-extension"></a>{}Escape-Sequenz / Markup-Erweiterung

Stellt die XAML-Escapesequenz für Attributwerte bereit. Die Escapesequenz ermöglicht es, die nachfolgenden Werte im Attribut als Literal zu interpretieren.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a>Verwendung von XAML-Eigenschaftenelementen

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|*literalValue*|Die Literalzeichenfolge, die der Escapesequenz folgt. In der Regel enthält diese Zeichenfolge eine offene oder schließende geschweifte Klammer (- oder .|

## <a name="remarks"></a>Bemerkungen

Die Escapesequenz{}( ) wird verwendet, damit eine offene geschweifte Klammer als Literalzeichen in XAML verwendet werden kann.

XAML-Reader verwenden in der Regel die offene geschweifte Klammer , um den Einstiegspunkt einer Markuperweiterung zu bezeichnen; sie überprüfen jedoch zuerst das nächste Zeichen, um festzustellen, ob es sich um eine schließende geschweifte Klammer handelt. Nur wenn die beiden{}geschweiften Klammern ( ) nebeneinander liegen, werden sie als Escapesequenz betrachtet.

Wenn die Escapesequenz gefunden wird, sollte der XAML-Reader den Rest der Zeichenfolge als Zeichenfolge verarbeiten. Wenn die Escapesequenz jedoch auf ein Element angewendet wird, das über einen Typkonverter verfügt, wird die Zeichenfolge möglicherweise typkonvertieren, wenn sie von einem XAML-Writer interpretiert wird.

Die Escapesequenz ist keine Markuperweiterung und wird nicht von einer Klasse unterstützt. Es handelt sich jedoch um eine Konvention, die XAML-Reader (einschließlich benutzerdefinierter XAML-Reader) beachten sollten.

Ein Anführungszeichen (") kann auf diese Weise nicht als Escapesequenz verwendet werden. Wenn Sie ein Anführungszeichen als Eigenschaftswert für eine Eigenschaftseigenschaft festlegen müssen, verwenden Sie die Eigenschaftenelementsyntax, und platzieren Sie das Anführungszeichen als Zeichenfolge innerhalb des Eigenschaftselements, oder verwenden Sie eine XML-Zeichenentität. Bei einer Content-Eigenschaft kann das Anführungszeichen der gesamte Inhalt sein.

Die Escapesequenz{}( ) ist häufig erforderlich, wenn ein XML-Typ angegeben wird, der einen Namespacequalifizierer an einem Speicherort enthalten muss, an dem eine XAML-Markuperweiterung angezeigt werden kann. Dieser Speicherort enthält den Start eines XAML-Attributwerts und in einer Markuperweiterung unmittelbar nach einem Gleichheitszeichen (=). Das folgende Beispiel zeigt Escapesequenzen für einen XML-Namespace, der am Anfang eines XAML-Attributwerts angezeigt wird.

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a>Weitere Informationen

- [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions.md)
- [XML-Zeichenentitäten und XAML](xml-character-entities.md)
