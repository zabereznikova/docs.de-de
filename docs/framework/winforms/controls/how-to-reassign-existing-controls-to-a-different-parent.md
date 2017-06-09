---
title: "Gewusst wie: Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen &#252;bergeordneten Element | Microsoft Docs"
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
  - "Containersteuerelemente, Windows Forms"
  - "Layout [Windows Forms], Ändern der Größe"
  - "Layout [Windows Forms], untergeordnete Steuerelemente"
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen &#252;bergeordneten Element
Sie können auf Ihrem Formular vorhandene Steuerelemente einem neuen Containersteuerelement zuordnen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element  
  
1.  Ziehen Sie drei <xref:System.Windows.Forms.Button>\-Steuerelemente aus der **Toolbox** auf das Formular.  
  
     Positionieren Sie sie nahe beieinander, ohne sie aber auszurichten.  
  
2.  Klicken Sie in der **Toolbox** auf das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements.  
  
     Ziehen Sie das Symbol nicht auf das Formular.  
  
3.  Bewegen Sie den Mauszeiger in die Nähe der drei <xref:System.Windows.Forms.Button>\-Steuerelemente.  
  
     Der Mauszeiger nimmt die Form eines Fadenkreuzes an, an das das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements angefügt ist.  
  
4.  Klicken Sie, und halten Sie die Maustaste gedrückt.  
  
5.  Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements zu zeichnen.  
  
6.  Ziehen Sie die Kontur um die drei <xref:System.Windows.Forms.Button>\-Steuerelemente.  
  
7.  Lassen Sie die Maustaste los.  
  
     Die drei <xref:System.Windows.Forms.Button>\-Steuerelemente werden jetzt in das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement eingefügt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)