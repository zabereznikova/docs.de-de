---
title: xml:space-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432701"
---
# <a name="xmlspace-handling-in-xaml"></a>xml:space-Behandlung in XAML

Das `xml:space` Attribut ist ein XML-definiertes Attribut, das das signifikante White-Space-Verarbeitungsverhalten innerhalb eines Objektelements deklariert. Dieses Verhalten ist für alle Inhalte (innerer `xml:space` Text) relevant, die im Element enthalten sind, in dem deklariert wird, sowie für Bereiche für untergeordnete Elemente.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object xml:space="preserve" />
```

 \- oder -

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>Bemerkungen

Die Definition `xml:space` für das Attribut in XAML einschließlich `xml:space` seiner beiden möglichen Werte wird von den W3C-Spezifikationen für XML als "special-Attribut" definiert.

Der Standardwert `xml:space` des Attributs `"default"`ist der Literalwert . Für den `"default"`Wert `xml:space` , oder wenn überhaupt nicht angegeben, ist das Verhalten einer signifikanten Leerraumanalyse die Standardbehandlung, wie im Thema [White-Space-Verarbeitung in XAML](white-space-processing.md)definiert.

Um Leerraum innerhalb des Objektelementinhalts beizubehalten, geben Sie `xml:space="preserve"` für dieses Objektelement an.

Bei den meisten `xml:space` Interpretationen werden die Attributeffekte und der Wert des Attributs auf untergeordnete Elemente beschränkt.

Eine vollständige Erläuterung der Whitespace-Verarbeitung in XAML finden Sie [unter Whitespace Processing in XAML](white-space-processing.md).

## <a name="see-also"></a>Weitere Informationen

- [Leerstellenverarbeitung in XAML](white-space-processing.md)
- [Übersicht über XAML (WPF)](../fundamentals/xaml.md)
