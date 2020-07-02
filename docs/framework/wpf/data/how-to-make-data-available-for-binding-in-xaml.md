---
title: 'Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden'
description: Entdecken Sie die verschiedenen Möglichkeiten, wie Sie Daten gemäß den Anforderungen Ihrer Anwendung in Windows Presentation Foundation (WPF) verfügbar machen können.
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 16618ce8b19f5dd5854c4d126e7fc455f0428a28
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620793"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden
In diesem Thema werden verschiedene Möglichkeiten erläutert, wie Sie Daten für die Bindung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] abhängig von den Anforderungen Ihrer Anwendung zur Verfügung stellen können.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie über ein Common Language Runtime (CLR)-Objekt verfügen, an das Sie eine Bindung [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] herstellen möchten, können Sie das Objekt auf eine Weise für die Bindung zur Verfügung stellen, indem Sie es als Ressource definieren und ihm ein-Objekt geben `x:Key` . Im folgenden Beispiel verfügen Sie über ein- `Person` Objekt mit der Zeichen folgen Eigenschaft `PersonName` . Das- `Person` Objekt (in der markierten Zeile, die das- `<src>` Element enthält) ist im-Namespace mit dem Namen definiert `SDKSample` .  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Anschließend können Sie das <xref:System.Windows.Controls.TextBlock> Steuerelement an das-Objekt in binden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , wie die markierte Zeile, die das-Element enthält, `<TextBlock>` anzeigt.
  
 Alternativ können Sie die- <xref:System.Windows.Data.ObjectDataProvider> Klasse verwenden, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Die Bindung wird auf die gleiche Weise definiert, wie die markierte Zeile, die das-Element enthält, `<TextBlock>` anzeigt.  
  
 In diesem speziellen Beispiel ist das Ergebnis identisch: Sie verfügen über eine <xref:System.Windows.Controls.TextBlock> mit dem Text Inhalt `Joe` . Die- <xref:System.Windows.Data.ObjectDataProvider> Klasse stellt jedoch Funktionen bereit, z. b. die Möglichkeit, eine Bindung an das Ergebnis einer Methode herzustellen. Sie können die-Klasse verwenden, <xref:System.Windows.Data.ObjectDataProvider> Wenn Sie die von ihr bereitgestellte Funktionalität benötigen.  
  
 Wenn Sie jedoch an ein Objekt binden, das bereits erstellt wurde, müssen Sie `DataContext` im Code festlegen, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Informationen zum Zugreifen auf XML-Daten für die Bindung mithilfe der <xref:System.Windows.Data.XmlDataProvider> -Klasse finden Sie unter [binden an XML-Daten mithilfe von XmlDataProvider-und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Informationen zum Zugreifen auf XML-Daten für die Bindung mithilfe der- <xref:System.Windows.Data.ObjectDataProvider> Klasse finden Sie unter [binden an XDocument, XElement oder LINQ für XML Query Ergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Informationen zu vielen Möglichkeiten, wie Sie die Daten angeben können, an die die Bindung erfolgen soll, finden Sie unter [angeben der Bindungs Quelle](how-to-specify-the-binding-source.md). Informationen zu den Datentypen, an die Sie binden können, oder zum Implementieren eigener Common Language Runtime (CLR)-Objekte für die Bindung finden Sie unter [Übersicht über Bindungs Quellen](binding-sources-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)
