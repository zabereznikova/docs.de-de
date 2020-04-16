---
title: xml:lang-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b5a06adbb7cb874bc09899118f13b91fbec7a85e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432707"
---
# <a name="xmllang-handling-in-xaml"></a>xml:lang-Behandlung in XAML

Das `xml:lang` Attribut ist ein XML-definiertes Attribut, das die Sprach- und Kulturinformationen für ein Element in XML deklariert. Das Attribut weist in XAML dieselbe Bedeutung auf, es müssen jedoch einige zusätzliche Aspekte berücksichtigt werden.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|*rfc3066lang*|Eine vom [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) -Standard abgeleitete Zeichenfolge, die entweder eine Sprache oder eine Kombination von Sprache-Region kennzeichnet. In letzterem Fall werden Sprache und Region durch einen einzelnen Bindestrich getrennt. Weitere Informationen zu den Werten und zum Format finden Sie unter <xref:System.Windows.Markup.XmlLanguage> .|

## <a name="remarks"></a>Bemerkungen

Die Definition `xml:lang` für [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] das Attribut `xml:lang` in wird vom World Wide Web Consortium (W3C) für XML als "Special-Attribut" abgeleitet. Informationen zu Sprache und Kultur werden von Elementen je nach deren Implementierung möglicherweise unterschiedlich verarbeitet. Es gibt jedoch keine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Standardverarbeitung für das `xml:lang` -Attribut.

Der Standardwert des `xml:lang` -Attributs ist eine leere Zeichenfolge auf Attributebene.

Die `xml:lang` -Attributeffekte und der Wert des Attributs werden im Allgemeinen in untergeordneten Elementen bewahrt, wenn sie von Systemen interpretiert werden, die auf `xml:lang` -Werte einwirken.

Wenn von XAML-Writern von .NET `xml:lang` XAML <xref:System.Windows.Markup.XmlLanguage> <xref:System.Globalization.CultureInfo> Services interpretiert wird, kann ein Wert oder Objekte in der zugrunde liegenden Objektdarstellung erstellen. Dieses Verhalten hängt jedoch davon ab, ob der angegebene `xml:lang` Wert eine gültige Konstruktion für diese Klassen ist.

Frameworks können zwischen den vom Framework definierten Eigenschaften und der Bedeutung der `xml:lang` in XML durch Anwenden von <xref:System.Windows.Markup.XmlLangPropertyAttribute> auf die Eigenschaft entsprechende Zuordnungen erstellen.

## <a name="wpf-usage-nodes"></a>Hinweise zur WPF-Verwendung

Für Elemente, die abgeleitete Klassen von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>darstellen, können Sie die entsprechende <xref:System.Windows.FrameworkElement.Language%2A> -Abhängigkeitseigenschaft anstelle des `xml:lang` -Attributs verwenden. Die <xref:System.Windows.FrameworkElement.Language%2A> -Eigenschaft verwendet standardmäßig „en-US“, wenn sie nicht anderweitig festgelegt wird. Dies erfolgt entweder über die Eigenschaft oder durch die Verarbeitung des `xml:lang` -Attributs.

## <a name="see-also"></a>Weitere Informationen

- [Globalisierung für WPF](../../framework/wpf/advanced/globalization-for-wpf.md)
