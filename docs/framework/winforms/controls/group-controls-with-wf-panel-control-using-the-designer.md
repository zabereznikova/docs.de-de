---
title: "Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer | Microsoft Docs"
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
  - "Panel-Steuerelement [Windows Forms], Gruppieren von Steuerelementen"
  - "Windows Forms-Steuerelemente, Gruppieren"
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer
<xref:System.Windows.Forms.Panel>\-Steuerelemente in Windows Forms werden zur Gruppierung anderer Steuerelemente verwendet.  Drei Gründe sprechen für das Gruppieren von Steuerelementen.  Erstens sorgt die visuelle Gruppierung zusammengehöriger Formularelemente für eine übersichtliche Benutzeroberfläche, zweitens können Elemente wie Optionsfelder programmgesteuert gruppiert werden und drittens können die Steuerelemente zur Entwurfszeit als Einheit verschoben werden.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie eine Gruppe von Steuerelementen  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.Panel>\-Steuerelement von der Registerkarte **Windows Forms** der Toolbox in ein Formular.  
  
2.  Fügen Sie dem Auswahlbereich weitere Steuerelemente hinzu, indem Sie diese im Auswahlbereich zeichnen.  
  
     Um bestehende Steuerelemente in einen Auswahlbereich aufzunehmen, wählen Sie alle Steuerelemente aus, schneiden sie aus und kopieren sie in die Zwischenablage. Wählen Sie dann das <xref:System.Windows.Forms.Panel>\-Steuerelement aus, und fügen Sie es in den Auswahlbereich ein.  Sie können Steuerelemente auch in den Auswahlbereich ziehen.  
  
3.  \(Optional\) Um einen Auswahlbereich mit einem Rahmen zu versehen, definieren Sie seine <xref:System.Windows.Forms.BorderStyle>\-Eigenschaft.  Es gibt drei Auswahlmöglichkeiten: <xref:System.Windows.Forms.BorderStyle>, <xref:System.Windows.Forms.BorderStyle> und <xref:System.Windows.Forms.BorderStyle>.  
  
## Siehe auch  
 [Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Übersicht über das Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Gewusst wie: Festlegen des Hintergrunds eines Bereichs](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)