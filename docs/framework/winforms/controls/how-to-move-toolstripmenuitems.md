---
title: 'Vorgehensweise: Verschieben von ToolStripMenuItems'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039796"
---
# <a name="how-to-move-toolstripmenuitems"></a>Vorgehensweise: Verschieben von ToolStripMenuItems
Zur Entwurfszeit können Sie ganze Menüs der obersten Ebene und ihre Menü Elemente an eine andere Stelle auf dem <xref:System.Windows.Forms.MenuStrip>verschieben. Sie können auch einzelne Menü Elemente zwischen Menüs der obersten Ebene verschieben oder die Position von Menü Elementen innerhalb eines Menüs ändern.

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>So verschieben Sie ein Menü der obersten Ebene und die zugehörigen Menü Elemente an eine andere Position der obersten Ebene

1. Klicken Sie mit der linken Maustaste auf das Menü, das Sie verschieben möchten.

2. Ziehen Sie die Einfügemarke in das Menü der obersten Ebene, das sich vor der beabsichtigten neuen Position befindet, und lassen Sie die linke Maustaste los.

     Das ausgewählte Menü wechselt nach rechts von der Einfügemarke.

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>So verschieben Sie ein Menü der obersten Ebene und die zugehörigen Menü Elemente an eine Dropdown-Position

1. Klicken Sie mit der linken Maustaste auf das Menü, das Sie verschieben möchten, und drücken Sie STRG + X, oder klicken Sie mit der rechten Maustaste auf das Menü, und wählen Sie aus dem Kontextmenü

2. Klicken Sie im Menü der obersten Ebene des Ziels mit der linken Maustaste auf das Menü Element oberhalb der vorgesehenen neuen Position, und drücken Sie STRG + V, oder klicken Sie mit der rechten Maustaste auf das Menü Element oberhalb der vorgesehenen neuen Position, und wählen Sie aus dem Kontextmenü **Einfügen** aus.

     Das Menü, das Sie Ausschneiden, wird nach dem ausgewählten Menü Element eingefügt.

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>So verschieben Sie ein Menü Element in einem Menü mithilfe des Items-Auflistungs-Editors

1. Klicken Sie mit der rechten Maustaste auf das Menü, das das Menü Element enthält, das Sie verschieben möchten.

2. Wählen Sie im Kontextmenü die Option **DropDownItems bearbeiten**aus.

3. Klicken Sie im Elementauflistungs- **Editor**mit der linken Maustaste auf das Menü Element, das Sie verschieben möchten.

4. Klicken Sie auf die Pfeiltasten nach oben und nach unten, um das Menü Element im Menü zu verschieben.

5. Klicken Sie auf **OK**.

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>So verschieben Sie ein Menü Element in einem Menü mithilfe der Tastatur

1. Halten Sie die Alt-Taste gedrückt.

2. Klicken Sie mit der linken Maustaste auf das Menü Element, das Sie verschieben möchten.

3. Ziehen Sie das Menü Element an die neue Stelle, und lassen Sie die linke Maustaste los.

## <a name="to-move-a-menu-item-to-another-menu"></a>So verschieben Sie ein Menü Element in ein anderes Menü

1. Klicken Sie mit der linken Maustaste auf das Menü Element, das Sie verschieben möchten, und drücken Sie STRG + X, oder klicken Sie mit der rechten Maustaste auf das Menü Element, und wählen Sie aus dem Kontextmenü aus

2. Klicken Sie mit der linken Maustaste auf das Menü, das das von Ihnen ausgeschnittene Menü Element enthalten soll.

3. Klicken Sie mit der linken Maustaste auf das Menü Element, das sich vor der beabsichtigten neuen Position befindet, und drücken Sie STRG + V, oder klicken Sie mit der rechten Maustaste auf das Menü Element vor der vorgesehenen neuen Position, und wählen Sie aus dem Kontextmenü **Einfügen** aus.

     Das Menü Element, das Sie Ausschneiden, wird nach dem ausgewählten Menü Element eingefügt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
