---
title: "Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht | Microsoft Docs"
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
  - "CollectionView, Navigieren in Objekten"
  - "Datenbindung, Navigieren durch die Objekte in einer Datenerfassungsansicht"
  - "Navigieren durch die Objekte in einer Datenerfassungsansicht"
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht
Mit Ansichten kann eine Datenerfassung abhängig von Sortierung, Filterung oder Gruppierung auf verschiedene Weise angezeigt werden.  Ansichten stellen auch einen Zeiger auf den aktuellen Datensatz bereit und ermöglichen das Verschieben des Zeigers.  In diesem Beispiel wird gezeigt, wie das aktuelle Objekt abgerufen wird und wie Sie mithilfe der von der <xref:System.Windows.Data.CollectionView>\-Klasse bereitgestellten Funktionalität durch die Objekte in einer Datenerfassung navigieren.  
  
## Beispiel  
 In diesem Beispiel ist `myCollectionView` ein <xref:System.Windows.Data.CollectionView>\-Objekt, das eine Ansicht für eine gebundene Auflistung ist.  
  
 Im folgenden Beispiel ist `OnButton` ein Ereignishandler für die `Previous`\-Schaltfläche und die `Next`\-Schaltfläche in einer Anwendung. Hierbei handelt es sich um Schaltflächen, mit denen der Benutzer in der Datenerfassung navigieren kann.  Beachten Sie, dass die <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A>\-Eigenschaft und die <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A>\-Eigenschaft berichten, ob der Zeiger für den aktuellen Datensatz am Anfang bzw. am Ende der Liste angekommen ist, sodass wie erforderlich entweder <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> oder <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> aufgerufen werden kann.  
  
 Die <xref:System.Windows.Data.CollectionView.CurrentItem%2A>\-Eigenschaft der Ansicht wird in eine `Order` umgewandelt, um das Element für die aktuelle Reihenfolge in der Erfassung zurückzugeben.  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)