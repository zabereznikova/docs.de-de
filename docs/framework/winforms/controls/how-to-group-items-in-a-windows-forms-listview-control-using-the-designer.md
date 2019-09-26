---
title: 'Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69039400"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers

Mit der Gruppierungs Funktion <xref:System.Windows.Forms.ListView> des-Steuer Elements können Sie Verwandte Gruppen von Elementen in Gruppen anzeigen. Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppen Kopfzeilen getrennt, die die Gruppentitel enthalten. Mithilfe von <xref:System.Windows.Forms.ListView> Gruppen können Sie die Navigation durch große Listen vereinfachen, indem Sie Elemente alphabetisch, nach Datum oder nach einer anderen logischen Gruppierung gruppieren. Die folgende Abbildung zeigt einige gruppierte Elemente:

![Zahlen, die in ungerade und gerade Gruppen aufgeteilt sind.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.ListView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

Um die Gruppierung zu aktivieren, müssen Sie zunächst ein oder <xref:System.Windows.Forms.ListViewGroup> mehrere Objekte entweder im Designer oder Programm gesteuert erstellen. Nachdem eine Gruppe definiert wurde, können Sie Ihr Elemente zuweisen.

> [!NOTE]
> <xref:System.Windows.Forms.ListView>Gruppen sind nur in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] verfügbar, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> -Methode aufruft. Unter früheren Betriebssystemen hat Code in Bezug auf Gruppen keine Auswirkung, und die Gruppen werden nicht angezeigt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.

## <a name="to-add-or-remove-groups-in-the-designer"></a>So können Sie Gruppen im Designer hinzufügen oder entfernen

1. Klicken Sie **im Eigenschaften** Fenster auf die Auslassungs Punkte![(die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der](./media/visual-studio-ellipsis-button.png)Eigenschaftenfenster von Visual Studio. <xref:System.Windows.Forms.ListView.Groups%2A> ) neben der-Eigenschaft.

     Der **ListViewGroup-Sammlungs-Editor** wird angezeigt.

2. Um eine Gruppe hinzuzufügen, klicken Sie auf die Schaltfläche **Hinzufügen** . Sie können dann Eigenschaften der neuen Gruppe festlegen, z. b. <xref:System.Windows.Forms.ListViewGroup.Header%2A> die <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> -Eigenschaft und die-Eigenschaft. Um eine Gruppe zu entfernen, wählen Sie Sie aus und klicken auf die Schaltfläche **Entfernen** .

## <a name="to-assign-items-to-groups-in-the-designer"></a>So weisen Sie Gruppen im Designer Elemente zu

1. Klicken Sie **im Eigenschaften** Fenster auf die Auslassungs Punkte![(die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der](./media/visual-studio-ellipsis-button.png)Eigenschaftenfenster von Visual Studio. <xref:System.Windows.Forms.ListView.Items%2A> ) neben der-Eigenschaft.

     Der **ListViewItem-Auflistungs-Editor** wird angezeigt.

2. Um ein neues Element hinzuzufügen, klicken Sie auf die Schaltfläche **Hinzufügen** . Sie können dann die Eigenschaften des neuen Elements festlegen, z. b <xref:System.Windows.Forms.ListViewItem.Text%2A> . <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> die-Eigenschaft und die-Eigenschaft.

3. Wählen Sie <xref:System.Windows.Forms.ListViewItem.Group%2A> die Eigenschaft aus, und wählen Sie eine Gruppe aus der Dropdown Liste aus.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem Windows Forms ListView-Steuerelement](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
