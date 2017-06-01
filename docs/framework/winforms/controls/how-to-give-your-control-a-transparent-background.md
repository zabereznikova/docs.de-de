---
title: "Gewusst wie: Verwenden eines transparenten Hintergrunds f&#252;r ein Steuerelement | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Transparenter Hintergrund"
  - "Transparenz, Benutzerdefinierte Windows Forms-Steuerelemente"
  - "Transparente Hintergründe, Benutzerdefinierte Steuerelemente"
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Gewusst wie: Verwenden eines transparenten Hintergrunds f&#252;r ein Steuerelement
In früheren Versionen von .NET Framework wird für Steuerelemente ein Festlegen auf transparente Hintergrundfarben nur dann unterstützt, wenn zunächst die <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode im Konstruktor der Formulare festgelegt wurde. In der aktuellen Framework\-Version kann die Hintergrundfarbe für die meisten Steuerelemente zur Entwurfszeit im Fenster **Eigenschaften** oder in Code im Konstruktor des Formulars auf <xref:System.Drawing.Color.Transparent%2A> festgelegt werden.  
  
> [!NOTE]
>  Windows Forms\-Steuerelemente unterstützen keine echte Transparenz. Der Hintergrund eines transparenten Windows Forms\-Steuerelements wird von seinem übergeordneten Element gezeichnet.  
  
> [!NOTE]
>  Das <xref:System.Windows.Controls.Button>\-Steuerelement unterstützt keine transparente Hintergrundfarbe, selbst wenn die <xref:System.Windows.Forms.ButtonBase.BackColor%2A>\-Eigenschaft auf <xref:System.Drawing.Color.Transparent%2A> festgelegt ist.  
  
### So weisen Sie dem Steuerelement eine transparente Hintergrundfarbe zu  
  
-   Wählen Sie im Eigenschaftenfenster die <xref:System.Windows.Forms.ButtonBase.BackColor%2A>\-Eigenschaft aus, und legen Sie diese auf <xref:System.Drawing.Color.Transparent%2A> fest.  
  
## Siehe auch  
 <xref:System.Drawing.Color.FromArgb%2A>   
 [Entwickeln benutzerdefinierter Windows Forms\-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Verwenden von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)   
 [Gewusst wie: Zeichnen deckender und halbtransparenter Linien](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)