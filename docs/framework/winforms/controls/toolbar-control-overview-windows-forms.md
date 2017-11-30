---
title: "Übersicht über das ToolBar-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 857cc04af6c619035fa2bf0a548053f57292f7bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="toolbar-control-overview-windows-forms"></a>Übersicht über das ToolBar-Steuerelement (Windows Forms)
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das <xref:System.Windows.Forms.ToolBar>-Steuerelement von Windows Forms wird in Formularen als eine Steuerleiste verwendet, auf der eine Zeile aus Dropdownmenüs und Bitmapschaltflächen angezeigt wird, die Befehle aktivieren. Daher kann ein Klicken auf eine Symbolleistenschaltfläche mit dem Auswählen eines Menübefehls identisch sein. Die Schaltflächen können so konfiguriert werden, dass sie so angezeigt werden und sich so verhalten wie Schaltflächen, Dropdownmenüs oder Trennzeichen. In der Regel enthält eine Symbolleiste Schaltflächen und Menüs, die Elementen in der Menüstruktur einer Anwendung entsprechen. Dadurch wird schneller Zugriff auf die am häufigsten verwendeten Funktionen und Befehle einer Anwendung ermöglicht.  
  
## <a name="working-with-the-toolbar-control"></a>Arbeiten mit dem ToolBar-Steuerelement  
 Ein <xref:System.Windows.Forms.ToolBar> Steuerelement ist in der Regel "angedockt" am oberen Rand des übergeordneten Fensters, aber sie können auch auf jeder Seite des Fensters angedockt werden. Eine Symbolleiste kann QuickInfos anzeigen, wenn der Benutzer mit dem Mauszeiger auf eine Schaltfläche der Symbolleiste zeigt. QuickInfos sind kleine Popupfenster, die den Zweck der Schaltfläche oder des Menüs kurz beschreiben. Zum Anzeigen von QuickInfos, die <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> Eigenschaft muss festgelegt werden, um `true`.  
  
> [!NOTE]
>  Bestimmte Anwendungen verfügen über mit der Symbolleiste vergleichbare Steuerelemente, die über dem Anwendungsfenster „gleiten“ und neu positioniert werden können. Das Windows Forms-Steuerelement „ToolBar“ kann diese Aktionen nicht ausführen.  
  
 Wenn die <xref:System.Windows.Forms.ToolBar.Appearance%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ToolBarAppearance>, die Schaltflächen die Symbolleiste angezeigt werden, als auch dreidimensionale ausgelöst. Sie können festlegen, die <xref:System.Windows.Forms.ToolBar.Appearance%2A> Eigenschaft von der Symbolleiste, um <xref:System.Windows.Forms.ToolBarAppearance> auf der Symbolleiste und der zugehörigen Schaltflächen Flatfile Stil. Wenn der Mauszeiger über eine flache Schaltfläche bewegt wird, wird die Schaltfläche dreidimensional dargestellt. Symbolleistenschaltflächen können mithilfe von Trennzeichen in logische Gruppen eingeteilt werden. Ein Trennzeichen ist eine Symbolleisten-Schaltfläche mit den <xref:System.Windows.Forms.ToolBarButton.Style%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ToolBarButtonStyle>. Es wird als leerer Zwischenraum auf der Symbolleiste dargestellt. Wenn die Symbolleiste flach dargestellt wird, werden die Trennlinien als Linien und nicht als Zwischenraum zwischen den Schaltflächen dargestellt.  
  
 Die <xref:System.Windows.Forms.ToolBar> Steuerelement ermöglicht es Ihnen das Erstellen von Symbolleisten durch Hinzufügen von <xref:System.Windows.Forms.Button> Datenbankobjekte in einem <xref:System.Windows.Forms.ToolBar.Buttons%2A> Auflistung. Können Sie den Auflistungs-Editor zum Hinzufügen von Schaltflächen zu einem <xref:System.Windows.Forms.ToolBar> Steuerelement; jede <xref:System.Windows.Forms.Button> Objekt müssen Text oder ein Bild zugewiesen, obwohl Sie beide zuweisen können. Das Bild wird von einer verknüpften [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)-Komponente zur Verfügung gestellt. Zur Laufzeit können Sie hinzufügen oder Entfernen von Schaltflächen aus dem <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> mithilfe der <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> und <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> Methoden. So programmieren Sie die Schaltflächen des eine <xref:System.Windows.Forms.ToolBar>, Code Hinzufügen der <xref:System.Windows.Forms.ToolBar.ButtonClick> Ereignisse der <xref:System.Windows.Forms.ToolBar>unter Verwendung der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> Eigenschaft von der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> Klasse, um zu bestimmen, welches Steuerelement die Schaltfläche geklickt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolBar>  
 [ToolBar-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [Gewusst wie: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 [Gewusst wie: Definieren eines Symbols für eine Symbolleistenschaltfläche](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)
