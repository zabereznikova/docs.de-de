---
title: "Gewusst wie: L&#246;schen von Bindungen | Microsoft Docs"
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
  - "Bindungen, Löschen"
  - "Löschen von Bindungen"
  - "Datenbindung, Löschen von Bindungen"
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: L&#246;schen von Bindungen
Dieses Beispiel zeigt, wie Bindungen aus einem Objekt gelöscht werden.  
  
## Beispiel  
 Um eine Bindung aus einer einzelnen Eigenschaft eines Objekts zu löschen, rufen Sie <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> wie im folgenden Beispiel gezeigt auf.  Im folgenden Beispiel wird die Bindung aus der <xref:System.Windows.Controls.TextBlock.TextProperty> des <xref:System.Windows.Controls.TextBlock>\-Objekts *mytext* entfernt.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Durch das Löschen einer Bindung wird diese entfernt, sodass die [Abhängigkeitseigenschaft](GTMT) einen außerhalb der Bindung gültigen Wert annimmt.  Dabei kann es sich um einen Standardwert, einen geerbten Wert oder um einen Wert aus einer Datenvorlagenbindung handeln.  
  
 Um Bindungen aus allen möglichen Eigenschaften eines Objekts zu löschen, verwenden Sie <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## Siehe auch  
 <xref:System.Windows.Data.BindingOperations>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)