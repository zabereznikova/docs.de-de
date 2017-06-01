---
title: "Gewusst wie: Abrufen der Standardansicht einer Datenauflistung | Microsoft Docs"
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
  - "Erstellen, Ansichten von Datenauflistungen"
  - "Datenbindung, Erstellen von Ansichten von Datenauflistungen"
  - "Datenauflistungen, Erstellen von Ansichten von"
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Abrufen der Standardansicht einer Datenauflistung
Mit Ansichten kann eine Datenerfassung abhängig von Sortierungs\-, Filterungs\- oder Gruppierungskriterien auf verschiedene Weise angezeigt werden.  Jede Auflistung verfügt über eine gemeinsame Standardansicht, die als tatsächliche Bindungsquelle verwendet wird, wenn eine Auflistung als Bindungsquelle angegeben wird.  Dieses Beispiel zeigt, wie die Standardansicht einer Auflistung abgerufen wird.  
  
## Beispiel  
 Zum Erstellen der Ansicht benötigen Sie einen Objektverweis auf die Auflistung.  Dieses Objekt kann abgerufen werden, indem Sie auf ein eigenes Code\-Behind\-Objekt verweisen oder den Datenkontext, eine Eigenschaft der Datenquelle oder eine Eigenschaft der Bindung abrufen.  Dieses Beispiel zeigt, wie der <xref:System.Windows.FrameworkElement.DataContext%2A> eines Datenobjekts abgerufen und direkt zum Abrufen der Standardansicht der Auflistung verwendet wird.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In diesem Beispiel ist das Stammelement ein <xref:System.Windows.Controls.StackPanel>.  <xref:System.Windows.FrameworkElement.DataContext%2A> wird auf *myDataSource* festgelegt und verweist auf einen Datenanbieter, der eine <xref:System.Collections.ObjectModel.ObservableCollection%601> von *Order*\-Objekten ist.  
  
 [!code-xml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Alternativ können Sie eine Instanziierung ausführen und mit der <xref:System.Windows.Data.CollectionViewSource>\-Klasse eine Bindung an Ihre eigene Auflistungsansicht herstellen.  Diese Auflistungsansicht ist nur für Steuerelemente freigegeben, die direkt daran gebunden sind.  Ein Beispiel finden Sie im Abschnitt "So erstellen Sie eine Ansicht" unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Beispiele für die Funktionalität, die von einer Auflistungsansicht bereitgestellt wird, finden Sie unter [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md) und [Navigieren durch die Objekte in einer Datenauflistungsansicht](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## Siehe auch  
 [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)