---
title: xml:lang-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: 92d1eda62ff394df54d9607bab46d9950681e603
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548207"
---
# <a name="xmllang-handling-in-xaml"></a>xml:lang-Behandlung in XAML

Das `xml:lang` -Attribut ist ein XML-definiertes Attribut, das die Sprach-und Kultur Informationen für ein Element in XML deklariert. Das Attribut weist in XAML dieselbe Bedeutung auf, es müssen jedoch einige zusätzliche Aspekte berücksichtigt werden.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|*rfc3066lang*|Eine vom [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) -Standard abgeleitete Zeichenfolge, die entweder eine Sprache oder eine Kombination von Sprache-Region kennzeichnet. In letzterem Fall werden Sprache und Region durch einen einzelnen Bindestrich getrennt. Weitere Informationen zu den Werten und zum Format finden Sie unter <xref:System.Windows.Markup.XmlLanguage> .|

## <a name="remarks"></a>Hinweise

Die Definition für das- `xml:lang` Attribut in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] wird von abgeleitet, `xml:lang` wie von der World Wide Web Consortium (W3C) for XML als "spezielles Attribut" definiert. Informationen zu Sprache und Kultur werden von Elementen je nach deren Implementierung möglicherweise unterschiedlich verarbeitet. Es gibt jedoch keine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Standardverarbeitung für das `xml:lang` -Attribut.

Der Standardwert des `xml:lang` -Attributs ist eine leere Zeichenfolge auf Attributebene.

Die `xml:lang` -Attributeffekte und der Wert des Attributs werden im Allgemeinen in untergeordneten Elementen bewahrt, wenn sie von Systemen interpretiert werden, die auf `xml:lang` -Werte einwirken.

Bei der Interpretation durch XAML-Writer von .net XAML-Diensten kann ein- `xml:lang` Wert-oder- <xref:System.Windows.Markup.XmlLanguage> <xref:System.Globalization.CultureInfo> Objekte in der zugrunde liegenden Objektdarstellung erstellen. dieses Verhalten hängt jedoch davon ab, ob der für angegebene Wert `xml:lang` eine gültige Konstruktion für diese Klassen ist.

Frameworks können zwischen den vom Framework definierten Eigenschaften und der Bedeutung der `xml:lang` in XML durch Anwenden von <xref:System.Windows.Markup.XmlLangPropertyAttribute> auf die Eigenschaft entsprechende Zuordnungen erstellen.

## <a name="wpf-usage-nodes"></a>Hinweise zur WPF-Verwendung

Für Elemente, die abgeleitete Klassen von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>darstellen, können Sie die entsprechende <xref:System.Windows.FrameworkElement.Language%2A> -Abhängigkeitseigenschaft anstelle des `xml:lang` -Attributs verwenden. Die <xref:System.Windows.FrameworkElement.Language%2A> -Eigenschaft verwendet standardmäßig „en-US“, wenn sie nicht anderweitig festgelegt wird. Dies erfolgt entweder über die Eigenschaft oder durch die Verarbeitung des `xml:lang` -Attributs.

## <a name="see-also"></a>Siehe auch

- [Globalisierung für WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
