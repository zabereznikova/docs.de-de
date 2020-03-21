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
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174185"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden
In diesem Thema werden verschiedene Möglichkeiten erläutert, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]wie Sie Daten für die Bindung in verfügbar machen können, je nach den Anforderungen Ihrer Anwendung.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie über ein CLR-Objekt (Common Language Runtime) verfügen, an das Sie von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]binden möchten, können Sie `x:Key`das Objekt als Bindung verfügbar machen, wenn Sie es als Ressource definieren und ihm eine geben. Im folgenden Beispiel haben `Person` Sie ein Objekt `PersonName`mit einer Zeichenfolgeneigenschaft mit dem Namen . Das `Person` Objekt (in der angezeigten `<src>` Hervorgehobenen Zeile, die `SDKSample`das Element enthält) wird im Namespace namens definiert.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Sie können das <xref:System.Windows.Controls.TextBlock> Steuerelement dann [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]an das Objekt in `<TextBlock>` binden, wie die hervorgehobene Zeile zeigt, die das Element enthält.
  
 Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> Klasse verwenden, wie im folgenden Beispiel:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Sie definieren die Bindung auf die gleiche Weise, wie die hervorgehobene Zeile, die das `<TextBlock>` Element enthält, zeigt.  
  
 In diesem speziellen Beispiel ist das Ergebnis <xref:System.Windows.Controls.TextBlock> das gleiche: `Joe`Sie haben eine mit dem Textinhalt . Die <xref:System.Windows.Data.ObjectDataProvider> Klasse stellt jedoch Funktionen bereit, z. B. die Möglichkeit, an das Ergebnis einer Methode zu binden. Sie können die <xref:System.Windows.Data.ObjectDataProvider> Klasse verwenden, wenn Sie die darin vorgesehene Funktionalität benötigen.  
  
 Wenn Sie jedoch an ein Objekt binden, das bereits erstellt `DataContext` wurde, müssen Sie den in-Code festlegen, wie im folgenden Beispiel.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Informationen zum Zugriff auf <xref:System.Windows.Data.XmlDataProvider> XML-Daten für die Bindung mithilfe der Klasse finden Sie unter [Binden an XML-Daten mithilfe eines XMLDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Informationen zum Zugriff auf <xref:System.Windows.Data.ObjectDataProvider> XML-Daten für die Bindung mithilfe der Klasse finden Sie unter [Binden an XDocument, XElement oder LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Weitere Informationen zu vielen Möglichkeiten, wie Sie die Daten angeben können, an die Sie binden, finden Sie unter [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md). Informationen dazu, an welche Datentypen Sie binden können oder wie Sie Ihre eigenen CLR-Objekte (Common Language Runtime) zur Bindung implementieren können, finden Sie unter [Übersicht über Bindungsquellen](binding-sources-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [How-to-Themen](data-binding-how-to-topics.md)
