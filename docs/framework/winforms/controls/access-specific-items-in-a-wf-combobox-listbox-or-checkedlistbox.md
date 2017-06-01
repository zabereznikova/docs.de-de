---
title: "Gewusst wie: Zugreifen auf spezifische Elemente in ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows&#160;Forms | Microsoft Docs"
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
  - "CheckedListBox-Steuerelement [Windows Forms], Zugreifen auf Elemente"
  - "Kombinationsfelder, Zugreifen auf Elemente"
  - "ComboBox-Steuerelement [Windows Forms], Zugreifen auf Elemente"
  - "Listenfelder, Zugreifen auf Elemente"
  - "ListBox-Steuerelement [Windows Forms], Zugreifen auf Elemente"
  - "ListBox-Steuerelement [Windows Forms], Zurückgeben von Elementinformationen"
ms.assetid: 1216742f-bcf9-4ff8-8a62-d7c9053c2b96
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Zugreifen auf spezifische Elemente in ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows&#160;Forms
Eine der grundlegenden Tasks ist das Zugreifen auf spezifische Elemente in Kombinationsfeldern, Listenfeldern oder aktivierten Listenfeldern von Windows Forms.  Sie können programmgesteuert bestimmen, welches Element sich an einer gegebenen Position in der Liste befindet.  
  
### So greifen Sie auf ein spezifisches Element zu  
  
1.  Fragen Sie die `Items` \-Auflistung mithilfe des Indizes des jeweiligen Elements ab:  
  
    ```vb  
    Private Function GetItemText(i As Integer) As String  
       ' Return the text of the item using the index:  
       Return ComboBox1.Items(i).ToString  
    End Function  
  
    ```  
  
    ```csharp  
    private string GetItemText(int i)  
    {  
       // Return the text of the item using the index:  
       return (comboBox1.Items[i].ToString());  
    }  
  
    ```  
  
    ```cpp  
    private:  
       String^ GetItemText(int i)  
       {  
          // Return the text of the item using the index:  
          return (comboBox1->Items->Item[i]->ToString());  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)