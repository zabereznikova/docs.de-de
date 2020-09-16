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
ms.openlocfilehash: d78c2fd63192dc499b119e5b038b92555511a695
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544803"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Systeminterner x:XData-XAML-Typ
Ermöglicht die Platzierung von XML-Dateninseln in einer XAML-Produktion. XML-Elemente in `x:XData` sollten nicht von XAML-Prozessoren behandelt werden, als ob Sie Teil des aktiven XAML-Standard Namespace oder eines anderen XAML-Namespace sind. `x:XData` kann beliebige wohlgeformte XML-Daten enthalten.

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
|`elementDataRoot`|Das einzelne Stamm Element der eingeschlossenen Daten Insel. Bei den meisten möglichen Consumern wird XML, das keinen einzelnen Stamm hat, als ungültig betrachtet. Insbesondere ist ein einzelner Stamm erforderlich, wenn der `x:XData` als XML-Datenquelle für WPF oder viele andere Technologien gedacht ist, die XML-Quellen für die Datenbindung verwenden.|
|`[elementData]`|Dies ist optional. XML-Code, der die XML-Daten darstellt. Eine beliebige Anzahl von Elementen kann als Elementdaten enthalten sein, und in anderen Elementen können sich auch die in der Tabelle enthaltenen Elemente befinden. Allerdings gelten die allgemeinen Regeln von XML.|

## <a name="remarks"></a>Hinweise

Die XML-Elemente in einem- `x:XData` Objekt können alle möglichen Namespaces und Präfixe des enthaltenden XMLDOM in den Daten erneut deklarieren.

Programm gesteuerter Zugriff auf XML-Daten und den systeminternen `x:XData` XAML-Typ ist in .net XAML-Diensten durch die- <xref:System.Windows.Markup.XData> Klasse möglich.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Das- `x:XData` Objekt wird primär als untergeordnetes Objekt eines <xref:System.Windows.Data.XmlDataProvider> oder alternativ als untergeordnetes Objekt der- <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Eigenschaft verwendet (in XAML wird dies in der Regel in der Eigenschafts Element Syntax ausgedrückt).

Die Daten sollten in der Regel den Basis-XML-Namespace innerhalb der Daten Insel neu definieren, sodass er ein neuer XML-Standard Namespace ist (auf eine leere Zeichenfolge festgelegt). Dies ist für einfache Dateninseln am einfachsten, weil die <xref:System.Windows.Data.Binding.XPath%2A> Ausdrücke, mit denen auf die Daten verwiesen und diese gebunden werden, die Einbindung von Präfixen vermeiden können. Komplexere Dateninseln definieren möglicherweise mehrere Präfixe für die Daten und verwenden ein bestimmtes Präfix für den XML-Namespace im Stammverzeichnis. In diesem Fall sollten alle <xref:System.Windows.Data.Binding.XPath%2A> Ausdrucks Verweise das entsprechende, Namespace zugeordnete Präfix enthalten. Weitere Informationen finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).

Technisch `x:XData` kann als Inhalt einer beliebigen Eigenschaft des Typs verwendet werden <xref:System.Xml.Serialization.IXmlSerializable> . Ist jedoch <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> die einzige bedeutende Implementierung.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.XmlDataProvider>
- [Übersicht über die Datenbindung](../data/data-binding-overview.md)
- [Bindungs Markup Erweiterung](/dotnet/desktop/wpf/advanced/binding-markup-extension)
