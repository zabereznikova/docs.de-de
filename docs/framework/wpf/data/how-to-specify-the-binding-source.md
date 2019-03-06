---
title: 'Vorgehensweise: Angeben der Bindungsquelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
ms.openlocfilehash: 105924fec2956f2f74a2a574ee62f71a37df9366
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356720"
---
# <a name="how-to-specify-the-binding-source"></a>Vorgehensweise: Angeben der Bindungsquelle
Bei der Datenbindung verweist das Bindungsquellenobjekt auf das Objekt, aus dem Sie Ihre Daten abrufen. In diesem Thema werden die verschiedenen Methoden zur Angabe der Bindungsquelle beschrieben.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie mehrere Eigenschaften an eine gemeinsame Quelle binden, sollten Sie die `DataContext`-Eigenschaft verwenden. Diese bietet eine bequeme Möglichkeit, einen Bereich festzulegen, in dem alle datengebundenen Eigenschaften eine gemeinsame Quelle erben.  
  
 Im folgenden Beispiel wird der Datenkontext für das Stammelement der Anwendung eingerichtet. Dies ermöglicht es allen untergeordneten Elementen, diesen Datenkontext zu erben. Die Daten für die Bindung werden aus einer benutzerdefinierten Datenklasse abgerufen (`NetIncome`), auf die direkt über eine Zuordnung verwiesen wird und die den Ressourcenschlüssel `incomeDataSource` erhält.  
  
 [!code-xaml[DirectionalBinding#DataContext1](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xaml[DirectionalBinding#DataContext2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 Im folgenden Beispiel wird die Definition der `NetIncome`-Klasse veranschaulicht.  
  
 [!code-csharp[DirectionalBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
>  Im vorherigen Beispiel wird das Objekt im Markup instanziiert und als Ressource verwendet. Wenn Sie eine Bindung zu einem Objekt erstellen möchten, das bereits im Code instanziiert wurde, müssen Sie die `DataContext`-Eigenschaft programmgesteuert festlegen. Ein Beispiel finden Sie unter [Bereitstellen von Daten, um diese in XAML zu binden](how-to-make-data-available-for-binding-in-xaml.md).  
  
 Wenn Sie alternativ die Quelle einzelner Bindungen explizit festlegen möchten, stehen Ihnen die folgenden Optionen zur Verfügung. Diese haben Vorrang gegenüber dem geerbten Datenkontext.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|Verwenden Sie diese Eigenschaft, um als Quelle die Instanz eines Objekts festzulegen. Wenn Sie nicht benötigen, dass die Funktionalität der Einrichtung eines Bereichs erbt die mehrere Eigenschaften denselben Datenkontext, können Sie verwenden die <xref:System.Windows.Data.Binding.Source%2A> -Eigenschaft anstelle der `DataContext` Eigenschaft. Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.Source%2A>.|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|Dies ist hilfreich, wenn Sie die Quelle relativ zum Speicherort Ihres Bindungsziels festlegen möchten. Sie können diese Eigenschaft beispielsweise verwenden, wenn Sie eine Eigenschaft Ihres Elements an eine andere Eigenschaft desselben Elements binden möchten oder wenn Sie eine Bindung in einem Stil oder einer Vorlage definieren möchten. Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.RelativeSource%2A>.|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|Sie geben eine Zeichenfolge an, die das Element darstellt, an das die Bindung erfolgen soll. Dies ist hilfreich, wenn Sie eine Bindung zur Eigenschaft eines anderen Elements Ihrer Anwendung erstellen möchten. Angenommen, Sie verwenden möchten eine <xref:System.Windows.Controls.Slider> steuern die Höhe eines anderen Steuerelements in der Anwendung oder wenn die Bindung erfolgen soll die <xref:System.Windows.Controls.ContentControl.Content%2A> des Steuerelements die <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Eigenschaft Ihre <xref:System.Windows.Controls.ListBox> Steuerelement. Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.ElementName%2A>.|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=nameWithType>
- [Vererbung von Eigenschaftswerten](../advanced/property-value-inheritance.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Übersicht über Bindungsdeklarationen](binding-declarations-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
