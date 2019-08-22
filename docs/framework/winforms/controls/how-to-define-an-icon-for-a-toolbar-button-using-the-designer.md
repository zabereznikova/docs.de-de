---
title: 'Vorgehensweise: Definieren eines Symbols für eine Symbolleistenschaltfläche mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666202"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Vorgehensweise: Definieren eines Symbols für eine Symbolleistenschaltfläche mithilfe des Designers

> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.

<xref:System.Windows.Forms.ToolBar>mithilfe von Schaltflächen können darin Symbole angezeigt werden, die von Benutzern leichter identifiziert werden können. Dies wird erreicht, indem der <xref:System.Windows.Forms.ImageList> Komponente Bilder hinzugefügt und dem <xref:System.Windows.Forms.ToolBar> Steuerelement zugeordnet wird.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.ToolBar> das ein- <xref:System.Windows.Forms.ImageList> Steuerelement und eine-Komponente enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>So legen Sie ein Symbol für eine Symbolleisten-Schaltfläche zur Entwurfszeit fest

1. Fügen Sie der <xref:System.Windows.Forms.ImageList> Komponente Bilder hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen oder Entfernen von ImageList-Bildern](how-to-add-or-remove-imagelist-images-with-the-designer.md)mit dem Designer.

2. Wählen Sie <xref:System.Windows.Forms.ToolBar> das Steuerelement auf dem Formular aus.

3. Legen Sie im Fenster **Eigenschaften** die- <xref:System.Windows.Forms.ToolBar> Eigenschaft des <xref:System.Windows.Forms.ToolBar.ImageList%2A> -Steuer Elements <xref:System.Windows.Forms.ImageList> auf die-Komponente fest.

4. Klicken Sie <xref:System.Windows.Forms.ToolBar> auf die-Eigenschaft des Steuer Elements, um es auszuwählen, und![klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (...)](./media/visual-studio-ellipsis-button.png)in der Eigenschaftenfenster von Visual Studio.), um den **ToolBarButton**- <xref:System.Windows.Forms.ToolBar.Buttons%2A> Auflistungs-Editor zu öffnen.

5. Mithilfe der Schaltfläche **Hinzufügen** können Sie dem <xref:System.Windows.Forms.ToolBar> Steuerelement Schaltflächen hinzufügen.

6. Legen Sie im Fenster **Eigenschaften** , das im Bereich auf der rechten Seite des **ToolBarButton**-Auflistungs-Editors <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> angezeigt wird, die-Eigenschaft jeder Symbolleisten-Schaltfläche auf einen der Werte in der Liste fest, der aus den Bildern gezeichnet wird, die Sie dem <xref:System.Windows.Forms.ImageList> Komponente.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolBar>
- [Vorgehensweise: Triggermenü Ereignisse für Symbolleisten-Schaltflächen](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar-Steuerelement](toolbar-control-windows-forms.md)
- [ImageList-Komponente](imagelist-component-windows-forms.md)
