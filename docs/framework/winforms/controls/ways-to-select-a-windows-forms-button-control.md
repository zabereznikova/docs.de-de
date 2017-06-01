---
title: "Methoden zur Auswahl eines Button-Steuerelements in Windows&#160;Forms | Microsoft Docs"
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
  - "Button-Steuerelement [Windows Forms], Auswählen"
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Methoden zur Auswahl eines Button-Steuerelements in Windows&#160;Forms
Eine Schaltfläche in Windows Forms kann wie folgt ausgewählt werden:  
  
-   Sie klicken mit der Maus auf die Schaltfläche.  
  
-   Sie aktivieren das <xref:System.Windows.Forms.Control.Click>\-Ereignis der Schaltfläche im Code.  
  
-   Sie verschieben den Fokus auf die Schaltfläche, indem Sie die TAB\-TASTE drücken und die Schaltfläche anschließend mit der LEERTASTE oder der EINGABETASTE auswählen.  
  
-   Sie drücken die für die Schaltfläche definierte Zugriffstasten \(ALT \+ unterstrichener Buchstabe\).  Weitere Informationen zu Zugriffstasten finden Sie unter [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Wenn es sich bei der Schaltfläche um die "Annehmen"\-Schaltfläche des Formulars handelt, können Sie sie durch Drücken der EINGABETASTE auswählen, und zwar selbst dann, wenn sich der Fokus auf einem anderen Steuerelement befindet. Dies ist jedoch nicht möglich, wenn das andere Steuerelement eine weitere Schaltfläche,  ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement ist, das die Eingabetaste auffängt.  
  
-   Wenn die Schaltfläche die "Abbrechen"\-Schaltfläche des Formulars ist, können Sie sie selbst dann mit ESC auswählen, wenn sich der Fokus auf einem anderen Steuerelement befindet.  
  
-   Um die Schaltfläche programmgesteuert auszuwählen, rufen Sie die <xref:System.Windows.Forms.Button.PerformClick%2A>\-Methode auf.  
  
## Siehe auch  
 [Übersicht über das Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)