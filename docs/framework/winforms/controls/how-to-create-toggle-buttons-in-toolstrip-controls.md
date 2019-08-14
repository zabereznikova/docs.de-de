---
title: 'Vorgehensweise: Erstellen von Umschaltflächen in ToolStrip-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 6a003b91cd4db5db2790a20db97dbaa4d8925e96
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972352"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>Vorgehensweise: Erstellen von Umschaltflächen in ToolStrip-Steuerelementen

Wenn ein Benutzer auf eine UMSCHALT Fläche klickt, wird er abgeversenkt angezeigt und behält die abgesendeten Darstellung bei, bis der Benutzer erneut auf die Schaltfläche klickt.

## <a name="to-create-a-toggling-toolstripbutton"></a>So erstellen Sie ein UMSCHALT Fläche-Tool Strip Button

- Verwenden Sie Code wie im folgenden Codebeispiel. In diesem Code wird davon ausgegangen, dass <xref:System.Windows.Forms.ToolStrip> das Formular ein-Steuer <xref:System.Windows.Forms.ToolStrip.Items%2A> Element enthält und dass `toolStripButton1`die zugehörige Auflistung einen <xref:System.Windows.Forms.ToolStripButton> aufgerufenen enthält Außerdem wird davon ausgegangen, dass Sie über einen Ereignis `toolStripButton1_CheckedChanged`Handler namens verfügen.

    ```vb
    toolStripButton1.CheckOnClick = True
    toolStripButton1.CheckedChanged AddressOf _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

    ```csharp
    toolStripButton1.CheckOnClick = true;
    toolStripButton1.CheckedChanged += new _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStripButton>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
