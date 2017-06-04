---
title: "Gewusst wie: Erstellen einer Bindung in Code | Microsoft Docs"
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
  - "Binden von Daten, Erstellen"
  - "Datenbindung, Erstellen"
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Gewusst wie: Erstellen einer Bindung in Code
In diesem Beispiel wird gezeigt, wie eine <xref:System.Windows.Data.Binding> in Code erstellt und festgelegt wird.  
  
## Beispiel  
 Die <xref:System.Windows.FrameworkElement>\-Klasse und die <xref:System.Windows.FrameworkContentElement>\-Klasse machen eine `SetBinding`\-Methode verfügbar.  Wenn Sie ein Element binden, das eine dieser Klassen erbt, können Sie die <xref:System.Windows.FrameworkElement.SetBinding%2A>\-Methode direkt aufrufen.  
  
 Im folgenden Beispiel wird eine Klasse mit dem Namen `MyData` erstellt, die eine Eigenschaft namens `MyDataProperty` enthält.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 Im folgenden Beispiel wird gezeigt, wie ein Bindungsobjekt erstellt wird, um die Quelle der Bindung festzulegen.  Im Beispiel wird <xref:System.Windows.FrameworkElement.SetBinding%2A> verwendet, um die <xref:System.Windows.Controls.TextBlock.Text%2A>\-Eigenschaft von `myText` \(ein <xref:System.Windows.Controls.TextBlock>\-Steuerelement\) an `MyDataProperty` zu binden.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Das vollständige Codebeispiel finden Sie unter [Code\-only Binding Sample](http://msdn.microsoft.com/de-de/764aaf0b-2216-4941-9548-9c98da18d1a6).  
  
 Anstatt <xref:System.Windows.FrameworkElement.SetBinding%2A> aufzurufen, können Sie die statische <xref:System.Windows.Data.BindingOperations.SetBinding%2A>\-Methode der <xref:System.Windows.Data.BindingOperations>\-Klasse verwenden.  Im folgenden Beispiel wird <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=fullName> anstelle von <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=fullName> aufgerufen, um `myText` an `myDataProperty` zu binden.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)