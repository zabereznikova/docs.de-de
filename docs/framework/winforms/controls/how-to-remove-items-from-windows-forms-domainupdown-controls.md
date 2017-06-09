---
title: "Gewusst wie: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms | Microsoft Docs"
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
  - "DomainUpDown-Steuerelement [Windows Forms], Entfernen von Elementen aus"
  - "Drehfeld-Steuerelement, Entfernen von Elementen"
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms
Sie können Elemente aus dem <xref:System.Windows.Forms.DomainUpDown>\-Steuerelement in Windows Forms entfernen, indem Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>\-Methode oder die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>\-Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>\-Klasse aufrufen.  Durch die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>\-Methode wird ein bestimmtes Element entfernt, während durch die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>\-Methode ein Element an einer bestimmten Position entfernt wird.  
  
### So entfernen Sie ein Element  
  
-   Mithilfe der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>\-Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>\-Klasse können Sie ein Element anhand seines Namens entfernen.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     \- oder \-  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>\-Methode, um ein Element anhand seiner Position zu entfernen.  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.DomainUpDown>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=fullName>   
 [DomainUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)   
 [Übersicht über das DomainUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)