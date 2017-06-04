---
title: "Gewusst wie: Binden an die Ergebnisse einer LINQ-Abfrage | Microsoft Docs"
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
  - "Binden an LINQ-Abfrageergebnisse [WPF]"
  - "Ausführen einer LINQ-Abfrage [WPF], Binden an Ergebnisse"
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Binden an die Ergebnisse einer LINQ-Abfrage
In diesem Beispiel wird veranschaulicht, wie Sie eine LINQ\-Abfrage ausführen und dann eine Bindung an die Ergebnisse vornehmen.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Listenfelder erstellt.  Das erste Listenfeld enthält drei Listenelemente.  
  
 [!code-xml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 Wenn Sie im ersten Listenfeld ein Element auswählen, wird der folgende Ereignishandler aufgerufen.  In diesem Beispiel steht `Tasks` für eine Auflistung von `Task`\-Objekten.  Die `Task`\-Klasse verfügt über eine Eigenschaft namens `Priority`.  Dieser Ereignishandler führt eine LINQ\-Abfrage aus, die die Auflistung von `Task`\-Objekten zurückgibt, die den ausgewählten Prioritätswert haben. Anschließend wird der Wert als <xref:System.Windows.FrameworkElement.DataContext%2A> festgelegt:  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 Das zweite Listenfeld wird an diese Auflistung gebunden, da der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Wert auf `{Binding}` festgelegt ist.  Als Ergebnis wird die zurückgegebene Auflistung angezeigt \(basierend auf `myTaskTemplate`<xref:System.Windows.DataTemplate>\).  
  
## Siehe auch  
 [Bereitstellen von Daten für die Bindung in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)   
 [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)   
 [Neues in WPF Version 4.5](../../../../docs/framework/wpf/getting-started/whats-new.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)