---
title: "Gewusst wie: Erstellen und Binden an ObservableCollection | Microsoft Docs"
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
  - "Klassen, ObservableCollection"
  - "Datenbindung, ObservableCollection-Klasse"
  - "Benachrichtigungen"
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erstellen und Binden an ObservableCollection
Dieses Beispiel veranschaulicht, wie Sie eine Auflistung erstellen und eine Bindung an eine Auflistung herstellen, die von der <xref:System.Collections.ObjectModel.ObservableCollection%601>\-Klasse abgeleitet wird, die Benachrichtigungen bereitstellt, wenn Elemente hinzugefügt oder entfernt werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die Implementierung einer `NameList`\-Auflistung veranschaulicht.  
  
 [!code-csharp[MultiBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[MultiBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameList.vb#1)]  
  
 Die Auflistung wird für die Bindung auf die gleiche Weise wie bei anderen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Objekten zur Verfügung gestellt. Informationen dazu finden Sie unter [Bereitstellen von Daten für die Bindung in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).  Sie können beispielsweise die Auflistung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] instanziieren und sie als Ressource, wie hier dargestellt, angeben:  
  
 [!code-xml[MultiBinding#OCHowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#ochowto)]  
[!code-xml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
  
 Danach können Sie eine Bindung an die Auflistung erstellen.  
  
 [!code-xml[MultiBinding#MultiBindingListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindinglistbox)]  
  
 Die Definition von `NameItemTemplate` wird an dieser Stelle nicht angezeigt.  
  
> [!NOTE]
>  Die Objekte in der Auflistung müssen die unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md) beschriebenen Anforderungen erfüllen.  Insbesondere müssen Sie bei der Verwendung von <xref:System.Windows.Data.BindingMode> oder <xref:System.Windows.Data.BindingMode> \(wenn Sie z. B. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dynamisch aktualisieren möchten, wenn sich die Quelleigenschaften ändern\) einen geeigneten Benachrichtigungsmechanismus bei einer Eigenschaftenänderung, z. B. die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle, implementieren.  
  
 Weitere Informationen finden Sie in [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md) unter Binden an Auflistungen.  
  
## Siehe auch  
 [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)