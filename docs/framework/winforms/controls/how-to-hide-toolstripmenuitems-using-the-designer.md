---
title: "Gewusst wie: Ausblenden von ToolStripMenuItems mithilfe des Designers | Microsoft Docs"
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
  - "Menüelemente, Ausblenden"
  - "MenuStrip-Steuerelement [Windows Forms], Ausblenden von Menüelementen im Designer"
  - "ToolStripMenuItems, Ausblenden von Menüelementen im Designer"
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Ausblenden von ToolStripMenuItems mithilfe des Designers
Durch das Ausblenden von Menüelementen können Sie die Benutzeroberfläche \(UI\) der Anwendung steuern und die verfügbaren Benutzerbefehle einschränken.  Häufig möchten Sie ein komplettes Menü ausblenden, wenn alle darin enthaltenen Menüelemente nicht verfügbar sind.  Dies ist weniger verwirrend für den Benutzer.  Des Weiteren möchten Sie das Menü oder Menüelement möglicherweise nicht nur ausblenden, sondern auch deaktivieren, da das Ausblenden den Benutzer nicht daran hindert, einen Menübefehl über eine Tastenkombination aufzurufen.  Weitere Informationen zum Deaktivieren von Menüelementen finden Sie unter [Gewusst wie: Deaktivieren von ToolStripMenuItems mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So blenden Sie ein Menü der obersten Ebene und seine Untermenüelemente aus  
  
1.  Wählen Sie das Menüelement der obersten Ebene aus, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Visible%2A>\-Eigenschaft oder <xref:System.Windows.Forms.ToolStripItem.Available%2A>\-Eigenschaft auf `false` fest.  
  
     Wenn Sie das Menüelement der obersten Ebene ausblenden, werden automatisch auch alle Menüelemente innerhalb dieses Menüs ausgeblendet.  Wenn Sie auf eine andere Stelle als dem <xref:System.Windows.Forms.MenuStrip> klicken, nachdem Sie <xref:System.Windows.Forms.ToolStripItem.Visible%2A> auf `false` festgelegt haben, werden das gesamte Menüelement der obersten Ebene und seine Untermenüelemente aus dem Formular ausgeblendet, was den Laufzeiteffekt Ihrer Aktion veranschaulicht.  Um das ausgeblendete Menüelement der obersten Ebene zur Entwurfszeit anzuzeigen, klicken Sie auf der **Komponentenleiste**, in der **Dokumentgliederung** oder am oberen Rand des Eigenschaftenrasters auf den <xref:System.Windows.Forms.MenuStrip>.  
  
> [!NOTE]
>  Es müssen nur selten ganze Menüs ausgeblendet werden. Ein Ausnahme hiervon bilden lediglich die untergeordneten Menüs beim Zusammenführen in einer MDI\-Anwendung.  
  
### So blenden Sie ein Untermenüelement aus  
  
1.  Wählen Sie das Untermenüelement aus, und legen Sie seine <xref:System.Windows.Forms.ToolStripItem.Visible%2A>\-Eigenschaft auf `false` fest.  
  
     Wenn Sie ein Untermenüelement ausblenden, bleibt es zur Entwurfszeit auf dem Formular sichtbar, sodass Sie es zur weiteren Arbeit leicht auswählen können.  Zur Laufzeit wird es ausgeblendet.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>   
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)   
 [Gewusst wie: Deaktivieren von ToolStripMenuItems mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)