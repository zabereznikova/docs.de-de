---
title: 'Vorgehensweise: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit'
description: Erfahren Sie, wie Sie Quick Infos für Steuerelemente Programm gesteuert oder in der Windows Forms-Designer in Visual Studio festlegen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 144ba5b6bffb4a538e345f7b2df4a453fc6fd63d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618024"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Gewusst wie: Festlegen von Quick Infos für Steuerelemente auf einem Windows Form zur Entwurfszeit

Sie können eine <xref:System.Windows.Forms.ToolTip> Zeichenfolge im Code oder in der Windows Forms-Designer in Visual Studio festlegen. Weitere Informationen zur <xref:System.Windows.Forms.ToolTip> Komponente finden Sie unter Übersicht über die [ToolTip-Komponente](tooltip-component-overview-windows-forms.md).

## <a name="set-a-tooltip-programmatically"></a>Programm gesteuertes Festlegen einer QuickInfo

1. Fügen Sie das Steuerelement hinzu, das die QuickInfo anzeigt.

2. Verwenden Sie die- <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der- <xref:System.Windows.Forms.ToolTip> Komponente.

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a>Festlegen einer QuickInfo im Designer

1. Fügen Sie in Visual Studio <xref:System.Windows.Forms.ToolTip> dem Formular eine Komponente hinzu.

2. Wählen Sie das Steuerelement aus, von dem die QuickInfo angezeigt wird, oder fügen Sie es dem Formular hinzu.

3. Legen Sie im Fenster **Eigenschaften** die QuickInfo **für den ToolTip1** -Wert auf eine entsprechende Text Zeichenfolge fest.

### <a name="to-remove-a-tooltip-programmatically"></a>So entfernen Sie eine QuickInfo Programm gesteuert

1. Verwenden Sie die- <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der- <xref:System.Windows.Forms.ToolTip> Komponente.

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a>Entfernen einer QuickInfo im Designer

1. Wählen Sie in Visual Studio das Steuerelement aus, das die QuickInfo anzeigt.

2. Löschen Sie im Fenster **Eigenschaften** den Text in der QuickInfo **auf ToolTip1**.

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die ToolTip-Komponente](tooltip-component-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [ToolTip-Komponente](tooltip-component-windows-forms.md)
