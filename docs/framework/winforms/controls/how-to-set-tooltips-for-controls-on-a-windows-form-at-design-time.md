---
title: 'Vorgehensweise: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211687"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Vorgehensweise: Festlegen von QuickInfos für Steuerelemente in Windows Forms zur Entwurfszeit

Sie können festlegen, eine <xref:System.Windows.Forms.ToolTip> Zeichenfolge im Code oder in Windows Forms-Designer in Visual Studio. Weitere Informationen zu den <xref:System.Windows.Forms.ToolTip> Komponente finden Sie unter [Übersicht über die ToolTip-Komponente](tooltip-component-overview-windows-forms.md).

## <a name="set-a-tooltip-programmatically"></a>Programmgesteuertes Festlegen einer QuickInfos

1. Fügen Sie das Steuerelement, das die QuickInfo angezeigt wird.

2. Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.

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

## <a name="set-a-tooltip-in-the-designer"></a>Festlegen einer QuickInfos im designer

1. Fügen Sie in Visual Studio eine <xref:System.Windows.Forms.ToolTip> -Komponente zum Formular.

2. Wählen Sie das Steuerelement, das die QuickInfo angezeigt, oder fügen Sie es dem Formular hinzu.

3. In der **Eigenschaften** legen die **QuickInfo auf ToolTip1** Wert, der eine entsprechende Zeichenfolge des Texts.

### <a name="to-remove-a-tooltip-programmatically"></a>Das programmgesteuerte Entfernen von einer QuickInfo

1. Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.

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

## <a name="remove-a-tooltip-in-the-designer"></a>Entfernen einer QuickInfos im designer

1. Wählen Sie in Visual Studio das Steuerelement, das die QuickInfo angezeigt wird.

2. In der **Eigenschaften** Fenster, löschen Sie den Text in die **QuickInfo auf ToolTip1**.

## <a name="see-also"></a>Siehe auch

- [Übersicht über die ToolTip-Komponente](tooltip-component-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente von Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [ToolTip-Komponente](tooltip-component-windows-forms.md)
