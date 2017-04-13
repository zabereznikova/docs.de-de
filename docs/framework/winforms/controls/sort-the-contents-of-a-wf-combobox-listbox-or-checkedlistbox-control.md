---
title: "Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows&#160;Forms | Microsoft Docs"
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
  - "CheckedListBox-Steuerelement [Windows Forms], Sortieren"
  - "Kombinationsfelder, Sortieren von Inhalten"
  - "ComboBox-Steuerelement [Windows Forms], Sortieren von Inhalten"
  - "Listenfelder, Sortieren von Inhalten"
  - "ListBox-Steuerelement [Windows Forms], Sortieren von Inhalten"
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows&#160;Forms
In datengebundenen Windows Forms\-Steuerelementen wird keine Sortierung durchgeführt.  Um sortierte Daten anzuzeigen, verwenden Sie eine Datenquelle, die die Sortierung unterstützt und lassen die Sortierung dann von der Datenquelle durchführen.  Folgende Datenquellen unterstützen die Sortierung: Datenansichten, Datenansichtmanager und sortierte Arrays.  
  
 Wenn das Steuerelement nicht datengebunden ist, können Sie es sortieren.  
  
### So sortieren Sie die Liste  
  
1.  Legen Sie die  `Sorted` \-Eigenschaft auf `true` fest.  
  
     Diese Einstellung ordnet alle vorhandenen Listenelemente in sortierter Reihenfolge an.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Datenbindung in Web Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)