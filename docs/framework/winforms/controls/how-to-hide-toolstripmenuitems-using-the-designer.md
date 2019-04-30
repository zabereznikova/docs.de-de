---
title: 'Vorgehensweise: Ausblenden von ToolStripMenuItems mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 31c597a0e2cbf41484f19c8d4179823e9fb929ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941205"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Vorgehensweise: Ausblenden von ToolStripMenuItems mithilfe des Designers
Ausblenden von Menüelementen ist eine Möglichkeit, die Benutzeroberfläche (UI) Ihrer Anwendung steuern und User-Befehle zu beschränken. Häufig möchten ein ganzes Menü ausblenden, wenn alle Menüelemente im auf nicht verfügbar sind. Dies führt zu weniger ablenkungen für den Benutzer. Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren Sie das Menü oder Menüelement, da allein durch das Ausblenden den Benutzer den Zugriff auf einen Menübefehl mit einer Tastenkombination nicht verhindert wird. Weitere Informationen zum Deaktivieren von Menüelementen, finden Sie unter [Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers](how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Um ein Menü der obersten Ebene und seine Untermenüelemente auszublenden.  
  
1. Wählen Sie das Menüelement der obersten Ebene, und legen dessen <xref:System.Windows.Forms.ToolStripItem.Visible%2A> oder <xref:System.Windows.Forms.ToolStripItem.Available%2A> Eigenschaft `false`.  
  
     Wenn Sie das Menüelement der obersten Ebene ausblenden, werden auch alle Menüelemente in diesem Menü ausgeblendet. Wenn Sie irgendwo anders als auf klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> nach dem Festlegen <xref:System.Windows.Forms.ToolStripItem.Visible%2A> zu `false`, die gesamte Menüelement der obersten Ebene und seine Untermenüelemente, die aus dem Formular zeigt Ihnen daher die Auswirkungen der Laufzeit Ihrer Aktion ausgeblendet werden. Um die ausgeblendeten Menüelement der obersten Ebene zur Entwurfszeit anzuzeigen, klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> in die **Komponentenleiste**im **Dokumentgliederung**, bzw. im oberen Bereich des Eigenschaftenrasters.  
  
> [!NOTE]
>  Sie werden nur selten ein ganzes Menü mit Ausnahme von mehrere untergeordnete Menüs mit Document Interface (MDI) in einem Szenario mit Zusammenführen ausblenden.  
  
### <a name="to-hide-a-submenu-item"></a>So blenden Sie ein Untermenüelement aus.  
  
1. Wählen Sie das Untermenüelement, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.  
  
     Wenn Sie ein Untermenüelement ausblenden, bleibt es auf das Formular zur Entwurfszeit angezeigt, damit Sie es einfach für die weitere Bearbeitung auswählen können. Es werden tatsächlich zur Laufzeit ausgeblendet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
- [Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers](how-to-disable-toolstripmenuitems-using-the-designer.md)
