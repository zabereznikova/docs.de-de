---
title: 'Vorgehensweise: Ausblenden von ToolStripMenuItems mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 968d34a5f79d469ef62beaa8ac96742d73391b22
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039746"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Vorgehensweise: Ausblenden von ToolStripMenuItems mithilfe des Designers
Das Ausblenden von Menü Elementen ist eine Möglichkeit, die Benutzeroberfläche (UI) Ihrer Anwendung zu steuern und Benutzer Befehle einzuschränken. Häufig ist es ratsam, ein gesamtes Menü auszublenden, wenn alle Menü Elemente darin nicht verfügbar sind. Dies stellt weniger Ablenkungen für den Benutzer dar. Außerdem empfiehlt es sich, das Menü oder das Menü Element auszublenden und zu deaktivieren, da durch das Ausblenden allein nicht verhindert wird, dass der Benutzer über eine Tastenkombination auf einen Menübefehl zugreift. Weitere Informationen zum Deaktivieren von Menü Elementen finden [Sie unter Gewusst wie: Deaktivieren Sie ToolStripMenuItems mithilfe des](how-to-disable-toolstripmenuitems-using-the-designer.md)Designers.

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>So blenden Sie ein Menü der obersten Ebene und seine unter Menü Elemente aus

1. Wählen Sie das Menü Element der obersten Ebene aus, <xref:System.Windows.Forms.ToolStripItem.Visible%2A> und <xref:System.Windows.Forms.ToolStripItem.Available%2A> legen Sie `false`die-oder-Eigenschaft auf fest

     Wenn Sie das Menü Element der obersten Ebene ausblenden, werden alle Menü Elemente in diesem Menü ebenfalls ausgeblendet. Wenn Sie auf eine andere Stelle als auf <xref:System.Windows.Forms.MenuStrip> der nach <xref:System.Windows.Forms.ToolStripItem.Visible%2A> - `false`Einstellung auf klicken, werden das gesamte Menü Element der obersten Ebene und seine unter Menü Elemente aus dem Formular entfernt, sodass Sie die Lauf Zeit Wirkung ihrer Aktion angezeigt werden. Um das ausgeblendete Menü Element der obersten Ebene zur Entwurfszeit anzuzeigen, <xref:System.Windows.Forms.MenuStrip> klicken Sie in der **Komponenten Leiste**, in der **Dokument**Gliederung oder am oberen Rand des Eigenschaften Rasters auf das.

> [!NOTE]
>  Sie werden in einem Zusammenführungs Szenario selten ein gesamtes Menü mit Ausnahme von untergeordneten MDI-Menüs (Multiple Document Interface) ausblenden.

## <a name="to-hide-a-submenu-item"></a>So blenden Sie ein unter Menü Element aus

1. Wählen Sie das unter Menü Element, und <xref:System.Windows.Forms.ToolStripItem.Visible%2A> legen Sie `false`dessen-Eigenschaft auf fest.

     Wenn Sie ein unter Menü Element ausblenden, bleibt es zur Entwurfszeit auf dem Formular sichtbar, sodass Sie es für weitere Aufgaben problemlos auswählen können. Sie wird zur Laufzeit ausgeblendet.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
- [Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers](how-to-disable-toolstripmenuitems-using-the-designer.md)
