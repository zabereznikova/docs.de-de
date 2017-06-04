---
title: "Gewusst wie: Bestimmen, ob ein Freezable-Objekt fixiert ist | Microsoft Docs"
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
  - "Freezable-Objekte, Feststellen ob fixiert"
  - "IsFrozen-Eigenschaft"
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Bestimmen, ob ein Freezable-Objekt fixiert ist
In diesem Beispiel wird dargestellt, wie Sie bestimmen können, ob ein <xref:System.Windows.Freezable>\-Objekt fixiert ist.  Wenn Sie ein fixiertes <xref:System.Windows.Freezable>\-Objekt bearbeiten möchten, wird eine <xref:System.InvalidOperationException> ausgelöst.  Sie können das Auslösen dieser Ausnahme verhindern, wenn Sie mithilfe der Eigenschaft <xref:System.Windows.Freezable.IsFrozen%2A> des <xref:System.Windows.Freezable>\-Objekts ermitteln, ob das Objekt fixiert ist.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.SolidColorBrush> fixiert und mithilfe der Eigenschaft <xref:System.Windows.Freezable.IsFrozen%2A> ermittelt, ob es fixiert ist.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Weitere Informationen über <xref:System.Windows.Freezable>\-Objekte finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.IsFrozen%2A>   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)