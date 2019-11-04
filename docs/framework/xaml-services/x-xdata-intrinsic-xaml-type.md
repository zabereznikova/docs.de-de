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
ms.openlocfilehash: 8496e7c87cf7e6eea996ca7af4f288b7495c7661
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459898"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Systeminterner x:XData-XAML-Typ
Ermöglicht die Platzierung von XML-Dateninseln in einer XAML-Produktion. XML-Elemente innerhalb `x:XData` sollten nicht von XAML-Prozessoren behandelt werden, als ob Sie Teil des aktiven XAML-Standard Namespace oder eines anderen XAML-Namespace sind. `x:XData` können beliebige wohlgeformte XML-Daten enthalten.  
  
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
 Die XML-Elemente in einem `x:XData` Objekt können alle möglichen Namespaces und Präfixe des enthaltenden XMLDOM innerhalb der Daten erneut deklarieren.  
  
 Programm gesteuerter Zugriff auf XML-Daten und den `x:XData` systeminternen XAML-Typ ist in .NET Framework XAML-Diensten durch die <xref:System.Windows.Markup.XData>-Klasse möglich.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Das `x:XData` Objekt wird primär als untergeordnetes Objekt eines <xref:System.Windows.Data.XmlDataProvider>oder alternativ als untergeordnetes Objekt der Eigenschaft <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> (in XAML) als untergeordnetes Objekt verwendet (in XAML wird dies in der Regel in der Eigenschafts Element Syntax ausgedrückt).  
  
 Die Daten sollten in der Regel den Basis-XML-Namespace innerhalb der Daten Insel neu definieren, sodass er ein neuer XML-Standard Namespace ist (auf eine leere Zeichenfolge festgelegt). Dies ist für einfache Dateninseln am einfachsten, da die <xref:System.Windows.Data.Binding.XPath%2A> Ausdrücke, die verwendet werden, um auf die Daten zu verweisen und diese zu binden, die Einbindung von Präfixen vermeiden können. Komplexere Dateninseln definieren möglicherweise mehrere Präfixe für die Daten und verwenden ein bestimmtes Präfix für den XML-Namespace im Stammverzeichnis. In diesem Fall sollten alle <xref:System.Windows.Data.Binding.XPath%2A> Ausdrucks Verweise das entsprechende, Namespace zugeordnete Präfix enthalten. Weitere Informationen finden Sie in der [Übersicht über die Datenbindung](../../desktop-wpf/data/data-binding-overview.md).  
  
 Technisch gesehen können `x:XData` als Inhalt einer beliebigen Eigenschaft des Typs <xref:System.Xml.Serialization.IXmlSerializable>verwendet werden. <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> ist jedoch die einzige bedeutende Implementierung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.XmlDataProvider>
- [Übersicht zur Datenbindung](../../desktop-wpf/data/data-binding-overview.md)
- [Bindung als Markuperweiterung](../wpf/advanced/binding-markup-extension.md)
