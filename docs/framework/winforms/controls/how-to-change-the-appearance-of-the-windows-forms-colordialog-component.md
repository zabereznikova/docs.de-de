---
title: "Gewusst wie: &#196;ndern der Darstellung der ColorDialog-Komponente in Windows&#160;Forms | Microsoft Docs"
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
  - "Farbe (Dialogfeld), Konfigurieren der Darstellung"
  - "ColorDialog-Komponente, Beispiele"
  - "ColorDialog-Komponente, Formatieren der Darstellung"
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: &#196;ndern der Darstellung der ColorDialog-Komponente in Windows&#160;Forms
Sie können die Darstellung der <xref:System.Windows.Forms.ColorDialog>\-Komponente in Windows Forms mithilfe einer Reihe zugehöriger Eigenschaften konfigurieren.  Das Dialogfeld verfügt über zwei Abschnitte. In einem Abschnitt werden die Grundfarben angezeigt, im anderen können benutzerdefinierte Farben festgelegt werden.  
  
 Durch die meisten Eigenschaften wird die Farbauswahl im Dialogfeld eingeschränkt.  Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>\-Eigenschaft auf `true` festgelegt wird, können die Benutzer benutzerdefinierte Farben festlegen.  Die <xref:System.Windows.Forms.ColorDialog.FullOpen%2A>\-Eigenschaft hat den Wert `true`, wenn das Dialogfeld zum Festlegen von benutzerdefinierten Farben erweitert wird. Andernfalls muss der Benutzer auf eine Schaltfläche "Benutzerdefinierte Farben" klicken.  Wenn für die <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>\-Eigenschaft der Wert `true` festgelegt wird, zeigt das Dialogfeld alle verfügbaren Grundfarben an.  Wird für die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>\-Eigenschaft `true` festgelegt, können keine Mischfarben, sondern nur Volltonfarben ausgewählt werden.  
  
 Wenn für die <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A>\-Eigenschaft `true` festgelegt wird, wird im Dialogfeld eine Hilfeschaltfläche angezeigt.  Durch Klicken auf die Hilfeschaltfläche löst der Benutzer das <xref:System.Windows.Forms.CommonDialog.HelpRequest>\-Ereignis der <xref:System.Windows.Forms.ColorDialog>\-Komponente aus.  
  
### So konfigurieren Sie die Darstellung des Farbdialogfelds  
  
1.  Legen Sie für die Eigenschaften <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> und <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> die gewünschten Werte fest.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog\-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)   
 [Übersicht über die ColorDialog\-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)