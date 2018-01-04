---
title: Systeminterner x:XData-XAML-Typ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: "17"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec46d0363e5b10d3bd3bd3f9c8f4d3694abc1c8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xxdata-intrinsic-xaml-type"></a>Systeminterner x:XData-XAML-Typ
Ermöglicht die Platzierung von XML-Dateninseln in einer XAML-Produktion. XML-Elemente im `x:XData` nicht durch Verwendung von XAML-Prozessoren behandelt werden soll, als wären sie Teil des agierenden standardmäßigen XAML-Namespace oder irgendeinen anderen XAML-Namespace. `x:XData`Dies können beliebiges wohlgeformtes XML enthalten.  
  
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
|`elementDataRoot`|Das einzelne Stammelement der eingeschlossenen Dateninsel. Für die meisten tatsächlichen Consumer wird XML, die keinen einzigen Stammknoten als ungültig betrachtet. Insbesondere ist ein einziger Stammknoten erforderlich, wenn die `x:XData` dient als eine XML-Datenquelle für WPF- oder vielen anderen Technologien, die XML-Datenquellen für die Datenbindung verwenden.|  
|`[elementData]`|Dies ist optional. XML-Datei, die die XML-Daten darstellt. Kann eine beliebige Anzahl von Elementen als Elementdaten enthalten sein, und geschachtelte Elemente können in andere Elemente enthalten sein. Allerdings gelten die allgemeinen Regeln des XML-Codes.|  
  
## <a name="remarks"></a>Hinweise  
 Die XML-Elemente innerhalb einer `x:XData` Objekt kann erneut deklarieren, alle möglichen Namespaces und Präfixe der enthaltenen XMLDOM in den Daten.  
  
 Programmgesteuerter Zugriff auf XML-Daten und die `x:XData` systeminterne XAML-Typ kann in .NET Framework-XAML-Dienste über die <xref:System.Windows.Markup.XData> Klasse.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Die `x:XData` Objekt dient in erster Linie als ein untergeordnetes Objekt des ein <xref:System.Windows.Data.XmlDataProvider>, oder alternativ das untergeordnete Objekt von der <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Eigenschaft (in XAML, dies ist i. d. r. ausgedrückt in Eigenschaftenelementsyntax).  
  
 Die Daten sollten in der Regel den Basis-XML-Namespace innerhalb der Dateninsel zu einer neuen XML-Namespace (festgelegt auf eine leere Zeichenfolge) definieren. Dies ist einfachste für einfache Datentypen Inseln, da die <xref:System.Windows.Data.Binding.XPath%2A> Ausdrücke, die zum Verweisen auf und Binden an die Daten verwendet werden können die Aufnahme von Präfixen vermeiden. Komplexere Dateninseln möglicherweise mehrere Präfixe für die Daten zu definieren und Verwenden von einem bestimmten Präfix für den XML-Namespace im Stammverzeichnis. In diesem Fall alle <xref:System.Windows.Data.Binding.XPath%2A> ausdrucksverweisen sollte das entsprechende zugeordneten Namespace-Präfix enthalten. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Technisch gesehen `x:XData` können verwendet werden, wie der Inhalt einer beliebigen Eigenschaft vom Typ <xref:System.Xml.Serialization.IXmlSerializable>. Allerdings <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> ist die einzige deutlich erkennbare-Implementierung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.XmlDataProvider>  
 [Übersicht zur Datenbindung](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Bindung als Markuperweiterung](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
