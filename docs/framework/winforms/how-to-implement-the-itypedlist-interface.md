---
title: "Gewusst wie: Implementieren der ITypedList-Schnittstelle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BindingList(Of T)-Klasse"
  - "Datenbindung, Implementieren"
  - "IBindingList-Schnittstelle"
  - "ITypedList-Schnittstelle"
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Implementieren der ITypedList-Schnittstelle
Implementieren Sie die <xref:System.ComponentModel.ITypedList>\-Schnittstelle, um die Schemaermittlung für eine bindbare Liste zu ermöglichen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die Implementierung der <xref:System.ComponentModel.ITypedList>\-Schnittstelle veranschaulicht.  Ein generischer Typ mit dem Namen `SortableBindingList` ist von der <xref:System.ComponentModel.BindingList%601>\-Klasse abgeleitet und implementiert die <xref:System.ComponentModel.ITypedList>\-Schnittstelle.  Eine einfache Klasse mit dem Namen `Customer` stellt Daten bereit, die an den Header eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements gebunden sind.  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweise auf die System.Drawing\-Assembly und die System.Windows.Forms\-Assembly.  
  
## Siehe auch  
 <xref:System.ComponentModel.ITypedList>   
 <xref:System.ComponentModel.BindingList%601>   
 <xref:System.ComponentModel.IBindingList>   
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)