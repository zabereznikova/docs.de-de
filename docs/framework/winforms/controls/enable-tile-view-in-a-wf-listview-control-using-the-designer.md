---
title: Aktivieren der Kachel Ansicht im ListView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745804"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Gewusst wie: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers
Mit der Kachel Ansicht des <xref:System.Windows.Forms.ListView>-Steuer Elements können Sie eine visuelle Balance zwischen grafischen und Textinformationen bereitstellen. Die textbasierten Daten, die für ein Element in der Ansicht "Nebeneinander" angezeigt werden, sind die gleichen wie die Spalteninformationen, die für die Detailansicht definiert wurden. Die Kachel Ansicht funktioniert in Kombination mit den Funktionen "Gruppieren" oder "Einfügemarke" im <xref:System.Windows.Forms.ListView> Steuerelement.

 In der Kachel Ansicht werden ein 32 x 32-Symbol und mehrere Textzeilen verwendet, wie in der folgenden Abbildung dargestellt.

 ![Ansicht „Nebeneinander“ in einem ListView-Steuerelement](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Symbole und Text der Ansicht "Nebeneinander"")

 Mit den Eigenschaften und Methoden der Kachel Ansicht können Sie angeben, welche Spalten Felder für die einzelnen Elemente angezeigt werden sollen. Darüber hinaus können Sie die Größe und Darstellung aller Elemente innerhalb eines Kachel Ansichts Fensters gemeinsam steuern. Aus Gründen der Übersichtlichkeit ist die erste Textzeile in einer Kachel immer der Name des Elements. Sie kann nicht geändert werden.

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.ListView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-set-tile-view-in-the-designer"></a>So legen Sie die Kachel Ansicht im Designer fest

1. Wählen Sie in Visual Studio das <xref:System.Windows.Forms.ListView>-Steuerelement auf dem Formular aus.

2. Wählen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.Windows.Forms.ListView.View%2A> aus, und wählen Sie dann die **Kachel**aus.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
