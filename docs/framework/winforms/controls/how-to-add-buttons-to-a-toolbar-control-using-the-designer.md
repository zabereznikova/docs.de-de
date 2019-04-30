---
title: 'Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: 509aa0b03dbbb370384fb83e0d8e5471fc2cb819
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011098"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Ein wesentlicher Bestandteil der <xref:System.Windows.Forms.ToolBar> Steuerelement ist, die Sie, damit hinzufügen Schaltflächen. Diese können verwendet werden, um den einfachen Zugriff auf Befehle im Menü, oder sie können alternativ abgelegt werden, in einem anderen Bereich der Benutzeroberfläche der Anwendung, um Befehle aus, um Ihre Benutzer verfügbar zu machen, die nicht in der Menüstruktur verfügbar sind.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.ToolBar> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-buttons-at-design-time"></a>Hinzufügen von Schaltflächen zur Entwurfszeit  
  
1. Wählen Sie das <xref:System.Windows.Forms.ToolBar>-Steuerelement.  
  
2. In der **Eigenschaften** Fenster, klicken Sie auf die <xref:System.Windows.Forms.ToolBar.Buttons%2A> Eigenschaft, um ihn auszuwählen, und klicken Sie auf die **mit den Auslassungspunkten** (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png " VbEllipsesButton")) die Schaltfläche, um die **ToolBarButton Auflistungs-Editor**.  
  
3. Verwenden der **hinzufügen** und **entfernen** Schaltflächen zum Hinzufügen und entfernen Schaltflächen aus der <xref:System.Windows.Forms.ToolBar> Steuerelement.  
  
4. Konfigurieren Sie die Eigenschaften der einzelnen Schaltflächen in der **Eigenschaften** Fenster, das im Bereich auf der rechten Seite des Editors angezeigt wird. Die folgende Tabelle zeigt einige wichtigen Eigenschaften zu berücksichtigen.  
  
    |Eigenschaft|Beschreibung|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Legt fest, klicken Sie im Menü auf das Dropdown-Symbolleisten-Schaltfläche angezeigt werden soll. Der Symbolleisten-Schaltfläche <xref:System.Windows.Forms.ToolBarButton.Style%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>. Diese Eigenschaft akzeptiert eine Instanz der <xref:System.Windows.Forms.ContextMenu> -Klasse als Verweis.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Legt fest, ob eine an-aus-Schaltfläche einer Symbolleiste teilweise gedrückt ist. Der Symbolleisten-Schaltfläche <xref:System.Windows.Forms.ToolBarButton.Style%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Legt fest, ob eine an-aus-Schaltfläche einer Symbolleiste gegenwärtig gedrückt ist. Der Symbolleisten-Schaltfläche <xref:System.Windows.Forms.ToolBarButton.Style%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> oder <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Legt das Format der Symbolleisten-Schaltfläche. Muss einer der Werte in der <xref:System.Windows.Forms.ToolBarButtonStyle> Enumeration.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Die Textzeichenfolge, die von der Schaltfläche angezeigt wird.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Der Text, der als QuickInfo für die Schaltfläche angezeigt wird.|  
  
5. Klicken Sie auf **OK** , um das Dialogfeld schließen und die angegebenen Bereiche zu erstellen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolBar>
- [Vorgehensweise: Definieren eines Symbols für eine Symbolleisten-Schaltfläche](how-to-define-an-icon-for-a-toolbar-button.md)
- [Vorgehensweise: Trigger Menüereignissen für Symbolleistenschaltflächen](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Übersicht über das ToolBar-Steuerelement](toolbar-control-overview-windows-forms.md)
- [ToolBar-Steuerelement](toolbar-control-windows-forms.md)
