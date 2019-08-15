---
title: 'Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: fd80a6543c83ae957cd9c51b068d0702559f0925
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040267"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers
Sie können die Befehle, die ein Benutzer durchführen kann, einschränken oder erweitern, indem Sie Menü Elemente als Reaktion auf Benutzeraktivitäten aktivieren und deaktivieren. Menü Elemente werden standardmäßig aktiviert, wenn Sie erstellt werden, aber dies kann über die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> -Eigenschaft angepasst werden. Sie können diese Eigenschaft zur Entwurfszeit im **Eigenschaften** Fenster oder Programm gesteuert bearbeiten, indem Sie Sie im Code festlegen. Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren Sie ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).

## <a name="to-disable-a-menu-item-at-design-time"></a>So deaktivieren Sie ein Menü Element zur Entwurfszeit

1. Wenn das Menü Element im Formular ausgewählt ist, legen Sie <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> die- `false`Eigenschaft auf fest.

    > [!TIP]
    >  Wenn Sie das erste Menü Element der obersten Ebene in einem Menü deaktivieren, werden alle im Menü enthaltenen Menü Elemente deaktiviert. Ebenso werden die unter Menü Elemente deaktiviert, wenn ein Menü Element mit unter Menü Elementen deaktiviert wird. Wenn alle Befehle in einem bestimmten Menü für den Benutzer nicht verfügbar sind, wird als bewährte Programmier Übung empfohlen, das gesamte Menü auszublenden und zu deaktivieren, da dadurch eine saubere Benutzeroberfläche dargestellt wird. Sie sollten das Menü ausblenden und deaktivieren, da durch das Ausblenden allein der Zugriff auf einen Menübefehl über eine Tastenkombination nicht verhindert wird. Legen Sie <xref:System.Windows.Forms.ToolStripItem.Visible%2A> die-Eigenschaft eines Menü Elements der obersten Ebene `false` auf fest, um das gesamte Menü auszublenden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Vorgehensweise: ToolStripMenuItems ausblenden](how-to-hide-toolstripmenuitems.md)
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
