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
ms.openlocfilehash: 97e878e4932ca9122bf27f76c32d1a56e69f253a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740606"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden
In diesem Thema werden verschiedene Möglichkeiten erläutert, wie Sie Daten in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]für die Bindung zur Verfügung stellen können, je nach den Anforderungen Ihrer Anwendung.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie über ein Common Language Runtime (CLR)-Objekt verfügen, an das Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]binden möchten, können Sie das Objekt auf eine Weise für die Bindung zur Verfügung stellen, indem Sie es als Ressource definieren und ihm einen `x:Key`bereitstellen. Im folgenden Beispiel verfügen Sie über ein `Person`-Objekt mit einer Zeichen folgen Eigenschaft namens `PersonName`. Das `Person`-Objekt (in der markierten Zeile, das das `<src>`-Element enthält) ist im Namespace mit dem Namen `SDKSample`definiert.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Anschließend können Sie das <xref:System.Windows.Controls.TextBlock>-Steuerelement an das-Objekt in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]binden, wie die markierte Zeile, die das `<TextBlock>`-Element enthält, anzeigt. 
  
 Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider>-Klasse verwenden, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Die Bindung wird auf die gleiche Weise definiert, wie die markierte Zeile, die das `<TextBlock>`-Element enthält.  
  
 In diesem speziellen Beispiel ist das Ergebnis identisch: Sie verfügen über eine <xref:System.Windows.Controls.TextBlock> mit dem Text Inhalt `Joe`. Die <xref:System.Windows.Data.ObjectDataProvider>-Klasse bietet jedoch Funktionen, wie z. b. die Möglichkeit, eine Bindung an das Ergebnis einer Methode herzustellen. Sie können die <xref:System.Windows.Data.ObjectDataProvider>-Klasse verwenden, wenn Sie die von ihr bereitgestellte Funktionalität benötigen.  
  
 Wenn Sie jedoch an ein Objekt binden, das bereits erstellt wurde, müssen Sie die `DataContext` im Code festlegen, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Informationen zum Zugreifen auf XML-Daten für die Bindung mithilfe der <xref:System.Windows.Data.XmlDataProvider>-Klasse finden Sie unter [binden an XML-Daten mithilfe von XmlDataProvider-und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Informationen zum Zugreifen auf XML-Daten für die Bindung mithilfe der <xref:System.Windows.Data.ObjectDataProvider>-Klasse finden Sie unter [binden an XDocument, XElement oder LINQ für XML Query Ergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Informationen zu vielen Möglichkeiten, wie Sie die Daten angeben können, an die die Bindung erfolgen soll, finden Sie unter [angeben der Bindungs Quelle](how-to-specify-the-binding-source.md). Informationen zu den Datentypen, an die Sie binden können, oder zum Implementieren eigener Common Language Runtime (CLR)-Objekte für die Bindung finden Sie unter [Übersicht über Bindungs Quellen](binding-sources-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
