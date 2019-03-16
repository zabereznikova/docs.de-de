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
ms.openlocfilehash: 68468c3c10fd884cf5fb92160e3cde41dbf7d529
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58030262"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Systeminterner x:XData-XAML-Typ
Ermöglicht die Platzierung von XML-Dateninseln innerhalb einer XAML-Produktion. XML-Elemente im `x:XData` sollten von XAML-Prozessoren nicht behandelt werden, als wären sie Teil der agierende Standard-XAML-Namespace oder irgendeinen anderen XAML-Namespace. `x:XData` kann beliebigen wohlgeformten XML-Code enthalten.  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`elementDataRoot`|Das einzelne Stammelement der Dateninsel eingeschlossen. XML, das keinen einzigen Stammknoten verfügt für die meisten Verbraucher "Eventual" wird als ungültig angesehen. Ein einziger Stammknoten ist insbesondere erforderlich, wenn die `x:XData` dient als eine XML-Datenquelle für WPF- oder viele andere Technologien, die XML-Datenquellen für die Datenbindung zu verwenden.|  
|`[elementData]`|Dies ist optional. XML-Code, der die XML-Daten darstellt. Kann eine beliebige Anzahl von Elementen als Elementdaten enthalten sein, und geschachtelte Elemente in anderen Elementen enthalten sein können; Allerdings gelten die allgemeinen Regeln des XML-Codes.|  
  
## <a name="remarks"></a>Hinweise  
 Die XML-Elemente innerhalb einer `x:XData` -Objekt kann erneut deklarieren, alle möglichen Namespaces und Präfixe der enthaltenden XMLDOM in den Daten.  
  
 Den programmgesteuerten Zugriff auf XML-Daten und die `x:XData` XAML-Grundtyp kann in .NET Framework-XAML-Dienste über die <xref:System.Windows.Markup.XData> Klasse.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Die `x:XData` Objekt wird in erster Linie als ein untergeordnetes Objekt verwendet einen <xref:System.Windows.Data.XmlDataProvider>, oder Sie können auch als untergeordnetes Objekt des der <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Eigenschaft (in XAML, dies ist in der Regel ausgedrückt in Eigenschaftenelement-Syntax).  
  
 Die Daten sollten in der Regel den XML-Namespace innerhalb der Dateninsel einer neuen XML-Namespace (festgelegt auf eine leere Zeichenfolge) definieren. Dies ist am einfachsten, für die einfache Daten Dateninseln, da die <xref:System.Windows.Data.Binding.XPath%2A> Ausdrücke, die zum Verweisen auf, und Binden an die Daten verwendet werden keine Einbeziehung von Präfixen. Komplexere Dateninseln möglicherweise mehrere Präfixe für die Daten definieren und Verwenden von einem bestimmten Präfix für den XML-Namespace im Stammverzeichnis. In diesem Fall alle <xref:System.Windows.Data.Binding.XPath%2A> ausdrucksverweisen sollte das entsprechende Namespace zugeordnete Präfix enthalten. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../wpf/data/data-binding-overview.md).  
  
 Technisch gesehen `x:XData` können verwendet werden, wie der Inhalt einer beliebigen Eigenschaft des Typs <xref:System.Xml.Serialization.IXmlSerializable>. Allerdings <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> ist die einzige deutlich erkennbare-Implementierung.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Data.XmlDataProvider>
- [Übersicht zur Datenbindung](../wpf/data/data-binding-overview.md)
- [Bindung als Markuperweiterung](../wpf/advanced/binding-markup-extension.md)
