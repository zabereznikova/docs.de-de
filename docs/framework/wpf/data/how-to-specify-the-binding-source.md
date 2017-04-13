---
title: "Gewusst wie: Angeben der Bindungsquelle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Binden von Daten, Bindungsquellen"
  - "Bindungsquellen"
  - "Datenbindung, Bindungsquelle"
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Angeben der Bindungsquelle
Bei der Datenbindung verweist das [Bindungsquellenobjekt](GTMT) auf das Objekt, von dem Sie die Daten abrufen.  In diesem Thema werden die verschiedenen Methoden zur Angabe der [Bindungsquelle](GTMT) beschrieben.  
  
## Beispiel  
 Wenn Sie mehrere Eigenschaften an eine gemeinsame Quelle binden, sollten Sie die `DataContext`\-Eigenschaft verwenden. Diese Eigenschaft bietet eine komfortable Möglichkeit, einen Bereich festzulegen, innerhalb dessen alle datengebundenen Eigenschaften eine gemeinsame Quelle erben.  
  
 Im folgenden Beispiel wird der Datenkontext auf dem Stammelement der Anwendung eingerichtet.  Dies ermöglicht es allen untergeordneten Elementen, diesen Datenkontext zu erben.  Die Daten für die Bindung werden aus einer benutzerdefinierten Datenklasse abgerufen \(`NetIncome`\), auf die direkt über eine Zuordnung verwiesen wird und die den Ressourcenschlüssel `incomeDataSource` erhält.  
  
 [!code-xml[DirectionalBinding#DataContext1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xml[DirectionalBinding#DataContext2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 Das folgende Beispiel zeigt die Definition der `NetIncome`\-Klasse.  
  
 [!code-csharp[DirectionalBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
>  Im vorherigen Beispiel wird das Objekt im Markup instanziiert und als Ressource verwendet.  Wenn Sie eine Bindung zu einem Objekt erstellen möchten, das bereits im Code instanziiert wurde, müssen Sie die `DataContext`\-Eigenschaft programmgesteuert festlegen.  Ein Beispiel finden Sie unter [Bereitstellen von Daten für die Bindung in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).  
  
 Wenn Sie die Quelle einzelner Bindungen explizit festlegen möchten, stehen Ihnen die folgenden Optionen zur Verfügung.  Diese haben Vorrang gegenüber dem geerbten Datenkontext.  
  
|Property|Beschreibung|  
|--------------|------------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|Verwenden Sie diese Eigenschaft, um als Quelle die Instanz eines Objekts festzulegen.  Wenn Sie keinen Bereich festlegen möchten, innerhalb dessen mehrere Eigenschaften denselben Datenkontext erben, können Sie die <xref:System.Windows.Data.Binding.Source%2A>\-Eigenschaft anstelle der `DataContext`\-Eigenschaft verwenden.  Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.Source%2A>.|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|Dies ist hilfreich, wenn Sie die Quelle relativ zum Standort Ihres [Bindungsziels](GTMT) festlegen möchten.  Sie können diese Eigenschaft beispielsweise verwenden, wenn Sie eine Eigenschaft Ihres Elements an eine andere Eigenschaft desselben Elements binden möchten oder wenn Sie eine Bindung in einem Stil oder einer Vorlage definieren möchten.  Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.RelativeSource%2A>.|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|Sie geben eine Zeichenfolge an, die das Element darstellt, an das die Bindung erfolgen soll.  Dies ist hilfreich, wenn Sie eine Bindung zur Eigenschaft eines anderen Elements Ihrer Anwendung erstellen möchten.  Wenn Sie z. B. einen <xref:System.Windows.Controls.Slider> verwenden möchten, um die Höhe eines anderen Steuerelements der Anwendung zu steuern, oder wenn Sie den <xref:System.Windows.Controls.ContentControl.Content%2A> des Steuerelements an die <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>\-Eigenschaft des <xref:System.Windows.Controls.ListBox>\-Steuerelements binden möchten.  Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.ElementName%2A>.|  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=fullName>   
 <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=fullName>   
 [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Bindungsdeklarationen](../../../../docs/framework/wpf/data/binding-declarations-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)