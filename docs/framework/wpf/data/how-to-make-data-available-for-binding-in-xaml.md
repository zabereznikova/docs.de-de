---
title: 'Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: dd66fb2f96f8c42fea36afaeda0aaf35a2adbace
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557328"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden
In diesem Artikel werden die verschiedenen Möglichkeiten können Sie Daten verfügbar machen für die Bindung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], abhängig von den Anforderungen Ihrer Anwendung.  
  
## <a name="example"></a>Beispiel  
 Ist eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekt aus binden möchten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], eine Möglichkeit, Sie können das Objekt verfügbar machen, für die Bindung bezieht sich auf die als Ressource zu definieren, und weisen Sie ihm eine `x:Key`. Im folgenden Beispiel haben Sie eine `Person` Objekt mit der eine Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`. Die `Person` -Objekt, das durch die hervorgehobene Zeile dargestellt wird, die enthält die `<src>` Element wird im Namespace namens definiert `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Sie können dann binden Sie die <xref:System.Windows.Controls.TextBlock> Steuerelement auf das Objekt in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], wie die hervorgehobene Zeile enthält die `<TextBlock>` Element zeigt. 
  
 Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> -Klasse, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Sie definieren die Bindung die gleiche Weise, wie die markierte Zeile, enthält die `<TextBlock>` Element zeigt.  
  
 In diesem speziellen Beispiel ist das Ergebnis identisch: Sie haben eine <xref:System.Windows.Controls.TextBlock> mit dem Textinhalt `Joe`. Allerdings die <xref:System.Windows.Data.ObjectDataProvider> -Klasse bietet eine Funktionalität, z. B. die Fähigkeit, auf das Ergebnis einer Methode zu binden. Sie können auch mithilfe der <xref:System.Windows.Data.ObjectDataProvider> Klasse, wenn Sie die Funktionalität benötigen.  
  
 Jedoch wenn Sie auf ein Objekt binden, der bereits erstellt wurde, müssen Sie legen die `DataContext` im Code, wie im folgenden Beispiel.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung unter Verwendung der <xref:System.Windows.Data.XmlDataProvider> Klasse, finden Sie unter [Binden mit XML-Daten mithilfe einer XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung unter Verwendung der <xref:System.Windows.Data.ObjectDataProvider> Klasse, finden Sie unter [binden, "XDocument" oder "XElement" mit LINQ für XML-Abfrageergebnissen](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Informationen über die verschiedenen Methoden können Sie angeben, die Daten, die Sie möchten binden, finden Sie unter [geben die Bindungsquelle](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md). Informationen zum welche Arten von Daten an Sie gebunden werden können, oder eine eigene Implementierung [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte für die Bindung, finden Sie unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
