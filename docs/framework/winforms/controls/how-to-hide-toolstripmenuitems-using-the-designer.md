---
title: 'Gewusst wie: Ausblenden von ToolStripMenuItems mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: b0018516b9ac337cea3716c4b2eddc6eb859dbb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534365"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Gewusst wie: Ausblenden von ToolStripMenuItems mithilfe des Designers
Ausblenden von Menüelementen ist eine Möglichkeit zum Steuern der Benutzeroberfläche (UI) Ihrer Anwendung, und Benutzerbefehle einschränken. Häufig, sollten Sie ein ganzes Menü auszublenden, wenn alle Menüelemente im auf ihm nicht verfügbar sind. Dies ist weniger verwirrend für den Benutzer. Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren das Menü oder Menüelement, wie durch das bloße Ausblenden nicht den Benutzer verhindert den Zugriff auf einen Menübefehl über eine Tastenkombination. Weitere Informationen zum Deaktivieren von Menüelementen, finden Sie unter [Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>So blenden Sie ein Menü der obersten Ebene und seine Untermenüelemente aus  
  
1.  Wählen Sie das Menüelement der obersten Ebene, und legen seine <xref:System.Windows.Forms.ToolStripItem.Visible%2A> oder <xref:System.Windows.Forms.ToolStripItem.Available%2A> Eigenschaft `false`.  
  
     Wenn Sie das Menüelement der obersten Ebene ausblenden, werden auch alle Menüelemente in diesem Menü ausgeblendet. Außer auf Klicken die <xref:System.Windows.Forms.MenuStrip> nach Einstellung <xref:System.Windows.Forms.ToolStripItem.Visible%2A> zu `false`, die gesamte Menüelement der obersten Ebene und seine Untermenüelemente verschwinden aus dem Formular dargestellt wird daher die Auswirkungen zur Laufzeit Ihre Aktion. Um die ausgeblendeten Menüelement der obersten Ebene zur Entwurfszeit anzuzeigen, klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> in der **Komponentenleiste**im **Dokumentgliederung**, oder am Anfang des Eigenschaftenrasters.  
  
> [!NOTE]
>  Sie werden nur selten ein gesamtes Menü außer mehrere untergeordnete Menüs mit Document Interface (MDI) in einem Szenario mit Zusammenführen ausblenden.  
  
### <a name="to-hide-a-submenu-item"></a>So blenden Sie ein Untermenüelement aus  
  
1.  Wählen Sie das Untermenüelement, und legen seine <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.  
  
     Wenn Sie ein Untermenüelement ausblenden, wird er auf das Formular zur Entwurfszeit angezeigt, damit Sie problemlos zur Bearbeitung auswählen können. Es werden tatsächlich zur Laufzeit ausgeblendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Gewusst wie: Deaktivieren von ToolStripMenuItems mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
