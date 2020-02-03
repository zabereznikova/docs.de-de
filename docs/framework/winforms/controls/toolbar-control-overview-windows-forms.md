---
title: Übersicht über das ToolBar-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: f364e052258703331496f8103b48953a90aa3a9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735484"
---
# <a name="toolbar-control-overview-windows-forms"></a>Übersicht über das ToolBar-Steuerelement (Windows Forms)
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das <xref:System.Windows.Forms.ToolBar>-Steuerelement von Windows Forms wird in Formularen als eine Steuerleiste verwendet, auf der eine Zeile aus Dropdownmenüs und Bitmapschaltflächen angezeigt wird, die Befehle aktivieren. Daher kann ein Klicken auf eine Symbolleistenschaltfläche mit dem Auswählen eines Menübefehls identisch sein. Die Schaltflächen können so konfiguriert werden, dass sie so angezeigt werden und sich so verhalten wie Schaltflächen, Dropdownmenüs oder Trennzeichen. In der Regel enthält eine Symbolleiste Schaltflächen und Menüs, die Elementen in der Menüstruktur einer Anwendung entsprechen. Dadurch wird schneller Zugriff auf die am häufigsten verwendeten Funktionen und Befehle einer Anwendung ermöglicht.  
  
## <a name="working-with-the-toolbar-control"></a>Arbeiten mit dem ToolBar-Steuerelement  
 Ein <xref:System.Windows.Forms.ToolBar> Steuerelement wird in der Regel am oberen Rand des übergeordneten Fensters "angedockt", aber es kann auch an eine beliebige Seite des Fensters angedockt werden. Eine Symbolleiste kann QuickInfos anzeigen, wenn der Benutzer mit dem Mauszeiger auf eine Schaltfläche der Symbolleiste zeigt. QuickInfos sind kleine Popupfenster, die den Zweck der Schaltfläche oder des Menüs kurz beschreiben. Um Quick Infos anzuzeigen, muss die <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A>-Eigenschaft auf `true`festgelegt werden.  
  
> [!NOTE]
> Bestimmte Anwendungen verfügen über mit der Symbolleiste vergleichbare Steuerelemente, die über dem Anwendungsfenster „gleiten“ und neu positioniert werden können. Das Windows Forms-Steuerelement „ToolBar“ kann diese Aktionen nicht ausführen.  
  
 Wenn die <xref:System.Windows.Forms.ToolBar.Appearance%2A>-Eigenschaft auf <xref:System.Windows.Forms.ToolBarAppearance>festgelegt ist, werden die Schaltflächen der Symbolleiste ausgelöst und dreidimensional angezeigt. Sie können die <xref:System.Windows.Forms.ToolBar.Appearance%2A>-Eigenschaft der Symbolleiste auf <xref:System.Windows.Forms.ToolBarAppearance> festlegen, um die Symbolleiste und die Schaltflächen flach zu gestalten. Wenn der Mauszeiger über eine flache Schaltfläche bewegt wird, wird die Schaltfläche dreidimensional dargestellt. Symbolleistenschaltflächen können mithilfe von Trennzeichen in logische Gruppen eingeteilt werden. Ein Trennzeichen ist eine Symbolleisten-Schaltfläche mit der <xref:System.Windows.Forms.ToolBarButton.Style%2A>-Eigenschaft auf <xref:System.Windows.Forms.ToolBarButtonStyle>. Es wird als leerer Zwischenraum auf der Symbolleiste dargestellt. Wenn die Symbolleiste flach dargestellt wird, werden die Trennlinien als Linien und nicht als Zwischenraum zwischen den Schaltflächen dargestellt.  
  
 Mit dem <xref:System.Windows.Forms.ToolBar>-Steuerelement können Sie Symbolleisten erstellen, indem Sie einer <xref:System.Windows.Forms.ToolBar.Buttons%2A> Auflistung <xref:System.Windows.Forms.Button>-Objekte hinzufügen. Mit dem Auflistungs-Editor können Sie einem <xref:System.Windows.Forms.ToolBar> Steuerelement Schaltflächen hinzufügen. jedem <xref:System.Windows.Forms.Button> Objekt muss Text oder ein Bild zugewiesen werden, obwohl Sie beide zuweisen können. Das Bild wird von einer verknüpften [ImageList](imagelist-component-windows-forms.md)-Komponente zur Verfügung gestellt. Zur Laufzeit können Sie mithilfe der Methoden <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> und <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> Schaltflächen der <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> hinzufügen oder entfernen. Um die Schaltflächen einer <xref:System.Windows.Forms.ToolBar>zu programmieren, fügen Sie dem <xref:System.Windows.Forms.ToolBar.ButtonClick>-Ereignis des <xref:System.Windows.Forms.ToolBar>Code hinzu, indem Sie die <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A>-Eigenschaft der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs>-Klasse verwenden, um zu bestimmen, auf welche Schaltfläche geklickt wurde.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ToolBar>
- [ToolBar-Steuerelement](toolbar-control-windows-forms.md)
- [Gewusst wie: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement](how-to-add-buttons-to-a-toolbar-control.md)
- [Gewusst wie: Definieren eines Symbols für eine Symbolleistenschaltfläche](how-to-define-an-icon-for-a-toolbar-button.md)
- [Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen](how-to-trigger-menu-events-for-toolbar-buttons.md)
