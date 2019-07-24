---
title: 'Vorgehensweise: Bereitstellen von Daten für die Bindung in XAML'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 3487a160cc49ab6b779a20157668915c2da33900
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401490"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Vorgehensweise: Bereitstellen von Daten für die Bindung in XAML
In diesem Thema werden verschiedene Möglichkeiten erläutert, wie Sie Daten für die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Bindung in abhängig von den Anforderungen Ihrer Anwendung zur Verfügung stellen können.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie über ein Common Language Runtime (CLR)-Objekt verfügen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], an das Sie eine Bindung herstellen möchten, können Sie das Objekt auf eine Weise für die Bindung zur Verfügung stellen, indem Sie es als Ressource definieren und ihm ein `x:Key`-Objekt geben. Im folgenden Beispiel verfügen Sie über ein `Person` -Objekt mit der Zeichen folgen `PersonName`Eigenschaft. Das `Person` -Objekt (in der markierten Zeile, die das `<src>` -Element enthält) ist im-Namespace `SDKSample`mit dem Namen definiert.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Anschließend können Sie das <xref:System.Windows.Controls.TextBlock> Steuerelement an das-Objekt in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]binden, wie die markierte Zeile, `<TextBlock>` die das-Element enthält, anzeigt. 
  
 Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> -Klasse verwenden, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Die Bindung wird auf die gleiche Weise definiert, wie die markierte Zeile, die `<TextBlock>` das-Element enthält, anzeigt.  
  
 In diesem speziellen Beispiel ist das Ergebnis identisch: Sie verfügen über eine <xref:System.Windows.Controls.TextBlock> mit dem Text Inhalt. `Joe` Die <xref:System.Windows.Data.ObjectDataProvider> -Klasse stellt jedoch Funktionen bereit, z. b. die Möglichkeit, eine Bindung an das Ergebnis einer Methode herzustellen. Sie können die <xref:System.Windows.Data.ObjectDataProvider> -Klasse verwenden, wenn Sie die von ihr bereitgestellte Funktionalität benötigen.  
  
 Wenn Sie jedoch an ein Objekt binden, das bereits erstellt wurde, müssen Sie `DataContext` im Code festlegen, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Informationen zum [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] zugreifen auf Daten für die <xref:System.Windows.Data.XmlDataProvider> Bindung mithilfe der-Klasse finden Sie unter [binden an XML-Daten mithilfe von XmlDataProvider-und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Informationen zum [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] zugreifen auf Daten für die <xref:System.Windows.Data.ObjectDataProvider> Bindung mithilfe der-Klasse finden Sie unter [binden an XDocument, XElement oder LINQ für XML Query Ergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Informationen zu vielen Möglichkeiten, wie Sie die Daten angeben können, an die die Bindung erfolgen soll, finden Sie unter [angeben der Bindungs Quelle](how-to-specify-the-binding-source.md). Informationen zu den Datentypen, an die Sie binden können, oder zum Implementieren eigener Common Language Runtime (CLR)-Objekte für die Bindung finden Sie unter [Übersicht über Bindungs Quellen](binding-sources-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
