---
title: "Gewusst wie: Programmgesteuertes Hinzuf&#252;gen von Elementen zu DomainUpDown-Steuerelementen in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DomainUpDown-Steuerelement [Windows Forms], Hinzufügen von Elementen zu"
  - "Drehfeld-Steuerelement, Hinzufügen von Elementen"
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Programmgesteuertes Hinzuf&#252;gen von Elementen zu DomainUpDown-Steuerelementen in Windows&#160;Forms
Sie können dem <xref:System.Windows.Forms.DomainUpDown>\-Steuerelement in Windows Forms im Code Elemente hinzufügen.  Rufen Sie die Methode <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>\-Klasse auf, um der <xref:System.Windows.Forms.DomainUpDown.Items%2A>\-Eigenschaft des Steuerelements Elemente hinzuzufügen.  Durch die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>\-Methode wird ein Element am Ende einer Auflistung hinzugefügt, während es durch die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>\-Methode an einer bestimmten Position eingefügt wird.  
  
### So fügen Sie ein neues Element hinzu  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>\-Methode, um ein Element am Ende der Elementliste hinzuzufügen.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     \- oder \-  
  
2.  Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>\-Methode, um ein Element an einer bestimmten Position in die Liste einzufügen.  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.DomainUpDown>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=fullName>   
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=fullName>   
 [DomainUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)   
 [Übersicht über das DomainUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)