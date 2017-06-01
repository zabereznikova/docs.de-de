---
title: "Gewusst wie: Anpassen der Gr&#246;&#223;e des Label-Steuerelements in Windows&#160;Forms an seinen Inhalt | Microsoft Docs"
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
  - "Beschriftungen, Größe anpassen"
  - "Label-Steuerelement [Windows Forms], Größe an Inhalt anpassen"
  - "Bezeichnungen, Größe an Inhalt anpassen"
  - "Größe, Steuerelemente"
  - "Festlegen der Größe von Steuerelementen"
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Anpassen der Gr&#246;&#223;e des Label-Steuerelements in Windows&#160;Forms an seinen Inhalt
Das <xref:System.Windows.Forms.Label>\-Steuerelement in Windows Forms kann eine oder mehrere Zeilen umfassen. Seine Größe ist entweder fest definiert oder kann automatisch an die Größe der Beschriftung angepasst werden.  Mit der <xref:System.Windows.Forms.Label.AutoSize%2A>\-Eigenschaft können Sie Steuerelemente an größere oder kleinere Beschriftungen anpassen. Dies ist besonders hilfreich, wenn sich die Beschriftung zur Laufzeit ändert.  
  
### So passen Sie die Größe eines Label\-Steuerelements dynamisch an die Größe seines Inhalts an  
  
1.  Legen Sie die entsprechende <xref:System.Windows.Forms.Label.AutoSize%2A>\-Eigenschaft auf `true` fest.  
  
 Wenn <xref:System.Windows.Forms.Label.AutoSize%2A> auf `false` festgelegt ist, werden die durch die <xref:System.Windows.Forms.Label.Text%2A>\-Eigenschaft festgelegten Wörter in die nächste Zeile \(falls vorhanden\) umbrochen. Die Größe des Steuerelements wird dabei nicht angepasst.  
  
## Siehe auch  
 [Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)   
 [Übersicht über das Label\-Steuerelement](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Label\-Steuerelement](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)