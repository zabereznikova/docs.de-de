---
title: "Gewusst wie: Gruppieren von Steuerelementen mit dem GroupBox-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Gruppieren"
  - "GroupBox-Steuerelement [Windows Forms], Gruppieren von Steuerelementen"
  - "Windows Forms-Steuerelemente, Gruppieren"
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Gruppieren von Steuerelementen mit dem GroupBox-Steuerelement in Windows&#160;Forms
<xref:System.Windows.Forms.GroupBox>\-Steuerelemente in Windows Forms werden zur Gruppierung anderer Steuerelemente verwendet.  Drei Gründe sprechen für das Gruppieren von Steuerelementen:  
  
-   Erstellen einer visuellen Gruppierung zusammengehöriger Formularelemente, um eine übersichtliche Benutzeroberfläche zu erhalten  
  
-   Erstellen programmgesteuerter Gruppierungen \(beispielsweise von Optionsfeldern\)  
  
-   Verschieben der Steuerelemente zur Entwurfszeit als eine Einheit  
  
### So erstellen Sie eine Gruppe von Steuerelementen  
  
1.  Zeichnen Sie in einem Formular ein <xref:System.Windows.Forms.GroupBox>\-Steuerelement.  
  
2.  Fügen Sie dem Gruppenfeld weitere Steuerelemente hinzu, indem Sie diese in das Gruppenfeld zeichnen.  
  
     Um vorhandene Steuerelemente in ein Gruppenfeld aufzunehmen, wählen Sie alle Steuerelemente aus, schneiden sie aus und kopieren sie in die Zwischenablage. Wählen Sie dann das <xref:System.Windows.Forms.GroupBox>\-Steuerelement aus, und fügen Sie die Steuerelemente in das Gruppenfeld ein.  Sie können Steuerelemente auch in das Gruppenfeld ziehen.  
  
3.  Legen Sie für die <xref:System.Windows.Forms.GroupBox.Text%2A>\-Eigenschaft des Gruppenfelds eine geeignete Beschriftung fest.  
  
## Siehe auch  
 <xref:System.Windows.Forms.GroupBox>   
 [GroupBox\-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)