---
title: "Wann ist ein Kombinationsfeld von Windows&#160;Forms dem Listenfeld vorzuziehen? | Microsoft Docs"
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
  - "Gebundene Steuerelemente, Kombinationsfelder"
  - "Kombinationsfelder, Im Vergleich zu Listenfeldern"
  - "ComboBox-Steuerelement [Windows Forms], Im Vergleich zu ListBox"
  - "ListBox-Steuerelement [Windows Forms], Zugreifen auf Elemente"
  - "ListBox-Steuerelement [Windows Forms], Hinzufügen und Entfernen von Elementen"
  - "ListBox-Steuerelement [Windows Forms], Im Vergleich zu ComboBox"
  - "ListCount-Eigenschaft"
  - "ListIndex-Eigenschaft"
  - "Windows Forms-Steuerelemente, Datenbindung"
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Wann ist ein Kombinationsfeld von Windows&#160;Forms dem Listenfeld vorzuziehen?
Die Steuerelemente <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> weisen ähnliche Verhaltensweisen auf und sind in einigen Fällen austauschbar.  Es gibt jedoch Situationen, in denen das eine besser geeignet ist als das andere.  
  
 Ein Kombinationsfeld empfiehlt sich immer dann, wenn eine Liste mit Auswahloptionen vorgeschlagen wird, und ein Listenfeld empfiehlt sich, wenn die Benutzereingaben auf das beschränkt sein sollen, was in der Liste steht.  Ein Kombinationsfeld enthält ein Textfeld, in das Optionen, die nicht in der Liste enthalten sind, eingegeben werden können,  sofern die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>\-Eigenschaft nicht auf <xref:System.Windows.Forms.ComboBoxStyle> festgelegt ist.  In diesem Fall wählt das Steuerelement ein Element aus, wenn Sie den ersten Buchstaben eingeben.  
  
 Darüber hinaus sparen Sie mit Kombinationsfeldern Platz in Formularen.  Da die Liste nur vollständig angezeigt wird, wenn der Benutzer auf den Abwärtspfeil klickt, findet ein Kombinationsfeld auch dort Platz, wo ein Listenfeld nicht mehr angezeigt werden kann.  Dies gilt nicht, wenn für die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>\-Eigenschaft <xref:System.Windows.Forms.ComboBoxStyle> festgelegt ist. In diesem Fall wird die ganze Liste angezeigt, und das Kombinationsfeld beansprucht mehr Platz als ein Listenfeld.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Gewusst wie: Sortieren des Inhalts eines ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)