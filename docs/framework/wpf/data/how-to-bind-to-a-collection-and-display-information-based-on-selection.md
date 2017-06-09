---
title: "Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl | Microsoft Docs"
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
  - "Datenbindung, Binden an Auflistungen"
  - "Datenbindung, Erstellen von Ansichten von Datenauflistungen"
  - "Datenbindung, Auswählen von Daten für Ansichten"
  - "Datenauflistungen, Auswählen von Daten für Ansichten"
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl
In einem einfachen Master\/Detail\-Szenario haben Sie ein datengebundenes <xref:System.Windows.Controls.ItemsControl>\-Element, z. B. ein <xref:System.Windows.Controls.ListBox>.  Auf Grundlage der Benutzerauswahl zeigen Sie weitere Informationen über das ausgewählte Element an.  In diesem Beispiel wird gezeigt, wie dieses Szenario implementiert wird.  
  
## Beispiel  
 In diesem Beispiel ist `People` eine <xref:System.Collections.ObjectModel.ObservableCollection%601> von `Person`\-Klassen.  Diese `Person`\-Klasse enthält drei Eigenschaften: `FirstName`, `LastName` und `HomeTown`, alle vom Typ `string`.  
  
 [!code-xml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 Das <xref:System.Windows.Controls.ContentControl> verwendet die folgende <xref:System.Windows.DataTemplate>, die definiert, wie die Informationen einer `Person` präsentiert werden:  
  
 [!code-xml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Im Folgenden finden Sie eine Bildschirmaufnahme der Ausgabe des Beispiels.  Das <xref:System.Windows.Controls.ContentControl>\-Element zeigt die anderen Eigenschaften der ausgewählten Person.  
  
 ![Binden an eine Auflistung](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding\_CollectionBindingSample")  
  
 Zwei Punkte sind in diesem Beispiel zu beachten:  
  
1.  Das <xref:System.Windows.Controls.ListBox> und das <xref:System.Windows.Controls.ContentControl> werden an dieselbe Quelle gebunden.  Die <xref:System.Windows.Data.Binding.Path%2A>\-Eigenschaften beider Bindungen sind nicht angegeben, da beide Steuerelemente an das gesamte Auflistungsobjekt gebunden werden.  
  
2.  Damit dies funktioniert, muss die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>\-Eigenschaft auf `true` festgelegt werden.  Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer als <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> festgelegt wird.  Wenn hingegen das <xref:System.Windows.Controls.ListBox> die Daten von <xref:System.Windows.Data.CollectionViewSource> abruft, werden Auswahl und Währung automatisch synchronisiert.  
  
 Beachten Sie, dass die `Person`\-Klasse die `ToString`\-Methode auf folgende Weise überschreibt.  Standardmäßig ruft das <xref:System.Windows.Controls.ListBox> `ToString` auf und zeigt eine Zeichenfolgendarstellung jedes Objekts in der gebundenen Auflistung an.  Aus diesem Grund wird jede `Person` im <xref:System.Windows.Controls.ListBox> als Vorname angezeigt.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## Siehe auch  
 [Verwenden des Master\-\/Detailmusters mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)   
 [Verwenden des Master\-\/Detailmusters mit hierarchischen XML\-Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)