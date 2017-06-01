---
title: "Gewusst wie: Implementieren von CompositeCollection | Microsoft Docs"
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
  - "Klassen, CompositeCollection"
  - "Datenbindung, CompositeCollection-Klasse"
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Implementieren von CompositeCollection
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mithilfe der <xref:System.Windows.Data.CompositeCollection>\-Klasse mehrere Auflistungen und Elemente als eine Liste angezeigt werden.  In diesem Beispiel ist `GreekGods` eine <xref:System.Collections.ObjectModel.ObservableCollection%601> von benutzerdefinierten `GreekGod`\-Objekten.  Es werden Datenvorlagen definiert, sodass `GreekGod`\-Objekte und `GreekHero`\-Objekte mit der Vordergrundfarbe Gold bzw. Zyan angezeigt werden.  
  
 [!code-xml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## Siehe auch  
 <xref:System.Windows.Data.CollectionContainer>   
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>   
 <xref:System.Windows.Data.XmlDataProvider>   
 <xref:System.Windows.DataTemplate>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)