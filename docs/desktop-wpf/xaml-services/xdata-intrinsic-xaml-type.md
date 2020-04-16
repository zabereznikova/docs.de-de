---
title: Systeminterner x:XData-XAML-Typ
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432791"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Systeminterner x:XData-XAML-Typ
Ermöglicht die Platzierung von XML-Dateninseln innerhalb einer XAML-Produktion. XML-Elemente `x:XData` innerhalb sollten von XAML-Prozessoren nicht so behandelt werden, als wären sie Teil des standardmäßigen XAML-Namespace oder eines anderen XAML-Namespace. `x:XData`kann beliebigewohle XML-Codes enthalten.

## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`elementDataRoot`|Das einzelne Stammelement der eingeschlossenen Dateninsel. Für die meisten Verbraucher gilt XML, das keinen einzelnen Stamm hat, als ungültig. Insbesondere ist ein einzelner Stamm `x:XData` erforderlich, wenn der als XML-Datenquelle für WPF oder viele andere Technologien gedacht ist, die XML-Quellen für die Datenbindung verwenden.|
|`[elementData]`|Optional. XML, das die XML-Daten darstellt. Eine beliebige Anzahl von Elementen kann als Elementdaten enthalten sein, und verschachtelte Elemente können in anderen Elementen enthalten sein. Es gelten jedoch die allgemeinen XML-Regeln.|

## <a name="remarks"></a>Bemerkungen

Die XML-Elemente `x:XData` innerhalb eines Objekts können alle möglichen Namespaces und Präfixe des enthaltenden XMLDOM in den Daten neu deklarieren.

Der programmgesteuerte Zugriff `x:XData` auf XML-Daten und den systeminternen XAML-Typ ist in .NET XAML Services über die <xref:System.Windows.Markup.XData> Klasse möglich.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Das `x:XData` Objekt wird in erster Linie <xref:System.Windows.Data.XmlDataProvider>als untergeordnetes Objekt eines verwendet, oder alternativ als untergeordnetes Objekt der <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Eigenschaft (in XAML wird dies in der Regel in der Eigenschaftselementsyntax ausgedrückt).

Die Daten sollten in der Regel den XML-Basisnamespace innerhalb der Dateninsel neu definieren, um ein neuer Standard-XML-Namespace zu werden (auf eine leere Zeichenfolge festgelegt). Dies ist für einfache <xref:System.Windows.Data.Binding.XPath%2A> Dateninseln am einfachsten, da die Ausdrücke, die zum Verweisen und Binden an die Daten verwendet werden, die Aufnahme von Präfixen vermeiden können. Komplexere Dateninseln können mehrere Präfixe für die Daten definieren und ein bestimmtes Präfix für den XML-Namespace im Stammverwenden verwenden. In diesem Fall <xref:System.Windows.Data.Binding.XPath%2A> sollten alle Ausdrucksverweise das entsprechende Präfix namespace-zugeordnet enthalten. Weitere Informationen finden Sie unter [Datenbindungsübersicht](../data/data-binding-overview.md).

Technisch kann `x:XData` als Inhalt jeder Eigenschaft des <xref:System.Xml.Serialization.IXmlSerializable>Typs verwendet werden. <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Dies ist jedoch die einzige prominente Umsetzung.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Data.XmlDataProvider>
- [Datenbindung sübersicht](../data/data-binding-overview.md)
- [Bindung als Markuperweiterung](../../framework/wpf/advanced/binding-markup-extension.md)
