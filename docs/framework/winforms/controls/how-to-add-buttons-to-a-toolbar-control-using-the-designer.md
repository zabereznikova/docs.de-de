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
ms.openlocfilehash: 4d7a49633599aabc96153e4793e50c1a4d6d092d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666222"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement mithilfe des Designers

> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.

Ein integraler Bestandteil des <xref:System.Windows.Forms.ToolBar> -Steuer Elements sind die Schaltflächen, die Sie hinzufügen. Diese können verwendet werden, um einen einfachen Zugriff auf Menübefehle bereitzustellen. Alternativ können Sie auch in einem anderen Bereich der Benutzeroberfläche der Anwendung platziert werden, um den Benutzern Befehle zur Verfügung zu stellen, die in der Menüstruktur nicht verfügbar sind.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.ToolBar> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

### <a name="to-add-buttons-at-design-time"></a>So fügen Sie zur Entwurfszeit Schaltflächen hinzu

1. Wählen Sie das <xref:System.Windows.Forms.ToolBar>-Steuerelement.

2. Klicken Sie **im Eigenschaften** Fenster auf die <xref:System.Windows.Forms.ToolBar.Buttons%2A> Eigenschaft, um Sie auszuwählen, und klicken Sie![auf die Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster](./media/visual-studio-ellipsis-button.png)von Visual Studio.), um **Toolbar Button zu öffnen. Sammlungs-Editor**.

3. Verwenden Sie die Schaltflächen **Hinzufügen** und **Entfernen** , um Schaltflächen <xref:System.Windows.Forms.ToolBar> im Steuerelement hinzuzufügen und zu entfernen.

4. Konfigurieren Sie die Eigenschaften der einzelnen Schaltflächen im **Eigenschaften** Fenster, das im Bereich auf der rechten Seite des Editors angezeigt wird. In der folgenden Tabelle sind einige wichtige Eigenschaften aufgeführt, die berücksichtigt werden müssen.

    |Eigenschaft|Beschreibung|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Legt das Menü fest, das in der Dropdown-Symbolleisten Schaltfläche angezeigt werden soll. Die-Eigenschaft der <xref:System.Windows.Forms.ToolBarButton.Style%2A> Symbolleisten-Schaltfläche <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>muss auf festgelegt werden. Diese Eigenschaft nimmt eine Instanz der <xref:System.Windows.Forms.ContextMenu> -Klasse als Verweis an.|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Legt fest, ob eine Symbolleisten Schaltfläche für ein-und ausschalten teilweise per pushübertragung Die-Eigenschaft der <xref:System.Windows.Forms.ToolBarButton.Style%2A> Symbolleisten-Schaltfläche <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>muss auf festgelegt werden.|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Legt fest, ob eine Symbolleisten Schaltfläche im gedrückten Stil aktuell im gedrückten Zustand ist. Die-Eigenschaft der <xref:System.Windows.Forms.ToolBarButton.Style%2A> Symbolleisten-Schaltfläche <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> muss <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>auf oder festgelegt werden.|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Legt den Stil der Symbolleisten Schaltfläche fest. Muss einer der Werte in der <xref:System.Windows.Forms.ToolBarButtonStyle> -Enumeration sein.|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Die von der Schaltfläche angezeigte Text Zeichenfolge.|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Der Text, der als QuickInfo für die Schaltfläche angezeigt wird.|

5. Klicken Sie auf **OK** , um das Dialogfeld zu schließen und die von Ihnen angegebenen Panels zu erstellen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolBar>
- [Vorgehensweise: Definieren eines Symbols für eine Symbolleisten-Schaltfläche](how-to-define-an-icon-for-a-toolbar-button.md)
- [Vorgehensweise: Triggermenü Ereignisse für Symbolleisten-Schaltflächen](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Übersicht über das ToolBar-Steuerelement](toolbar-control-overview-windows-forms.md)
- [ToolBar-Steuerelement](toolbar-control-windows-forms.md)
