---
title: Übersicht über das ToolBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: 7b39c8e3dca88e968b43ba5ff14794e2e77247d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174810"
---
# <a name="toolbar-control-overview-windows-forms"></a>Übersicht über das ToolBar-Steuerelement (Windows Forms)
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das <xref:System.Windows.Forms.ToolBar>-Steuerelement von Windows Forms wird in Formularen als eine Steuerleiste verwendet, auf der eine Zeile aus Dropdownmenüs und Bitmapschaltflächen angezeigt wird, die Befehle aktivieren. Daher kann ein Klicken auf eine Symbolleistenschaltfläche mit dem Auswählen eines Menübefehls identisch sein. Die Schaltflächen können so konfiguriert werden, dass sie so angezeigt werden und sich so verhalten wie Schaltflächen, Dropdownmenüs oder Trennzeichen. In der Regel enthält eine Symbolleiste Schaltflächen und Menüs, die Elementen in der Menüstruktur einer Anwendung entsprechen. Dadurch wird schneller Zugriff auf die am häufigsten verwendeten Funktionen und Befehle einer Anwendung ermöglicht.  
  
## <a name="working-with-the-toolbar-control"></a>Arbeiten mit dem ToolBar-Steuerelement  
 Ein <xref:System.Windows.Forms.ToolBar> Steuerelement ist in der Regel "angedockt" am oberen Rand des übergeordneten Fensters, aber sie können auch auf jeder Seite des Fensters angedockt werden. Eine Symbolleiste kann QuickInfos anzeigen, wenn der Benutzer mit dem Mauszeiger auf eine Schaltfläche der Symbolleiste zeigt. QuickInfos sind kleine Popupfenster, die den Zweck der Schaltfläche oder des Menüs kurz beschreiben. Zum Anzeigen von QuickInfos der <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> Eigenschaft muss festgelegt werden, um `true`.  
  
> [!NOTE]
>  Bestimmte Anwendungen verfügen über mit der Symbolleiste vergleichbare Steuerelemente, die über dem Anwendungsfenster „gleiten“ und neu positioniert werden können. Das Windows Forms-Steuerelement „ToolBar“ kann diese Aktionen nicht ausführen.  
  
 Wenn die <xref:System.Windows.Forms.ToolBar.Appearance%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ToolBarAppearance>, die Symbolleisten-Schaltflächen angezeigt werden, erhöht und dreidimensional. Sie können festlegen, die <xref:System.Windows.Forms.ToolBar.Appearance%2A> Eigenschaft von der Symbolleiste, um <xref:System.Windows.Forms.ToolBarAppearance> gerne die Symbolleiste und deren Schaltflächen flach dargestellt. Wenn der Mauszeiger über eine flache Schaltfläche bewegt wird, wird die Schaltfläche dreidimensional dargestellt. Symbolleistenschaltflächen können mithilfe von Trennzeichen in logische Gruppen eingeteilt werden. Ein Trennzeichen ist eine Symbolleisten-Schaltfläche mit den <xref:System.Windows.Forms.ToolBarButton.Style%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ToolBarButtonStyle>. Es wird als leerer Zwischenraum auf der Symbolleiste dargestellt. Wenn die Symbolleiste flach dargestellt wird, werden die Trennlinien als Linien und nicht als Zwischenraum zwischen den Schaltflächen dargestellt.  
  
 Die <xref:System.Windows.Forms.ToolBar> Steuerelement ermöglicht es Ihnen zum Erstellen von Symbolleisten hinzufügen <xref:System.Windows.Forms.Button> Objekte eine <xref:System.Windows.Forms.ToolBar.Buttons%2A> Auflistung. Können Sie den Auflistungs-Editor auf die Schaltflächen zum Hinzufügen einer <xref:System.Windows.Forms.ToolBar> Steuerelement; jede <xref:System.Windows.Forms.Button> -Objekt sollte Text oder ein Bild zugewiesen ist, können, jedoch auch beides zuweisen können. Das Bild wird von einer verknüpften [ImageList](imagelist-component-windows-forms.md)-Komponente zur Verfügung gestellt. Zur Laufzeit können Sie hinzufügen oder entfernen Sie Schaltflächen aus der <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> mithilfe der <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> und <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> Methoden. Programmieren die Schaltflächen des eine <xref:System.Windows.Forms.ToolBar>, fügen Sie Code in die <xref:System.Windows.Forms.ToolBar.ButtonClick> Ereignisse der <xref:System.Windows.Forms.ToolBar>unter Verwendung der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> Eigenschaft der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> Klasse, um zu bestimmen, welche Schaltfläche geklickt wurde.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolBar>
- [ToolBar-Steuerelement](toolbar-control-windows-forms.md)
- [Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement](how-to-add-buttons-to-a-toolbar-control.md)
- [Vorgehensweise: Definieren eines Symbols für eine Symbolleisten-Schaltfläche](how-to-define-an-icon-for-a-toolbar-button.md)
- [Vorgehensweise: Trigger Menüereignissen für Symbolleistenschaltflächen](how-to-trigger-menu-events-for-toolbar-buttons.md)
