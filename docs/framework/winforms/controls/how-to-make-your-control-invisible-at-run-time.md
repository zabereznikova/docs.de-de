---
title: "Gewusst wie: Ausblenden des Steuerelements zur Laufzeit | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Ausblenden zur Laufzeit"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Unsichtbar"
  - "Unsichtbare Steuerelemente"
  - "Laufzeit, Ausblenden von Steuerelementen"
  - "Benutzersteuerelemente [Windows Forms], Unsichtbar"
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Ausblenden des Steuerelements zur Laufzeit
In einigen Fällen muss ein Benutzersteuerelement erstellt werden, das zur Laufzeit ausgeblendet ist.  Ein Steuerelement, das einen Wecker darstellt, muss z. B. nur bei Ertönen des Alarmsignals sichtbar sein.  Dies kann einfach durch Festlegen der <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft erzielt werden.  Wenn für die <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft der Wert `true` festgelegt wurde, wird das Steuerelement normal angezeigt.  Bei `false` wird das Steuerelement ausgeblendet.  Das Steuerelement kann zwar auch in ausgeblendetem Zustand aktiviert sein, Sie können dann jedoch mit diesem nicht über die Benutzeroberfläche interagieren.  Wenn Sie ein Steuerelement erstellen möchten, das dennoch auf Benutzereingaben reagiert \(z. B. auf Mausklicks\), muss es sich bei diesem um ein transparentes Steuerelement handeln.  Weitere Informationen finden Sie unter [Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).  
  
### So blenden Sie das Steuerelement zur Laufzeit aus  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft auf `false` fest.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.Visible%2A>   
 [Entwickeln benutzerdefinierter Windows Forms\-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)