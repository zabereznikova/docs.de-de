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
ms.openlocfilehash: c5f729837b9bb52ca7d232ca66b58e283a2bcefc
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053699"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Systeminterner x:XData-XAML-Typ
Ermöglicht die Platzierung von XML-Dateninseln in einer XAML-Produktion. XML-Elemente `x:XData` in sollten nicht von XAML-Prozessoren behandelt werden, als ob Sie Teil des aktiven XAML-Standard Namespace oder eines anderen XAML-Namespace sind. `x:XData`kann beliebige wohlgeformte XML-Daten enthalten.  
  
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
|`[elementData]`|Optional. XML-Code, der die XML-Daten darstellt. Eine beliebige Anzahl von Elementen kann als Elementdaten enthalten sein, und in anderen Elementen können sich auch die in der Tabelle enthaltenen Elemente befinden. Allerdings gelten die allgemeinen Regeln von XML.|  
  
## <a name="remarks"></a>Hinweise  
 Die XML-Elemente in `x:XData` einem-Objekt können alle möglichen Namespaces und Präfixe des enthaltenden XMLDOM in den Daten erneut deklarieren.  
  
 Programm gesteuerter Zugriff auf XML- `x:XData` Daten und den systeminternen XAML-Typ ist in .NET Framework XAML-Diensten durch die <xref:System.Windows.Markup.XData> -Klasse möglich.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Das `x:XData` -Objekt wird primär als untergeordnetes Objekt <xref:System.Windows.Data.XmlDataProvider>eines oder alternativ als <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> untergeordnetes Objekt der-Eigenschaft verwendet (in XAML wird dies in der Regel in der Eigenschafts Element Syntax ausgedrückt).  
  
 Die Daten sollten in der Regel den Basis-XML-Namespace innerhalb der Daten Insel neu definieren, sodass er ein neuer XML-Standard Namespace ist (auf eine leere Zeichenfolge festgelegt). Dies ist für einfache Dateninseln am einfachsten, <xref:System.Windows.Data.Binding.XPath%2A> weil die Ausdrücke, mit denen auf die Daten verwiesen und diese gebunden werden, die Einbindung von Präfixen vermeiden können. Komplexere Dateninseln definieren möglicherweise mehrere Präfixe für die Daten und verwenden ein bestimmtes Präfix für den XML-Namespace im Stammverzeichnis. In diesem Fall sollten alle <xref:System.Windows.Data.Binding.XPath%2A> Ausdrucks Verweise das entsprechende, Namespace zugeordnete Präfix enthalten. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../wpf/data/data-binding-overview.md).  
  
 Technisch kann als Inhalt einer beliebigen Eigenschaft des Typs <xref:System.Xml.Serialization.IXmlSerializable>verwendet werden. `x:XData` <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Ist jedoch die einzige bedeutende Implementierung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.XmlDataProvider>
- [Übersicht zur Datenbindung](../wpf/data/data-binding-overview.md)
- [Bindung als Markuperweiterung](../wpf/advanced/binding-markup-extension.md)
