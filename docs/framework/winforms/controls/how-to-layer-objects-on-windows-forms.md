---
title: 'Vorgehensweise: Überlagern von Objekten in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: 818f36633575b248d92da475c462cc0f211fe969
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966540"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Vorgehensweise: Überlagern von Objekten in Windows Forms
Beim Erstellen einer komplexen Benutzeroberfläche oder bei Verwendung eines MDI-Formulars (Multiple Document Interface) empfiehlt es sich, sowohl Steuerelemente als auch untergeordnete Formulare zu verlagern, um komplexere Benutzeroberflächen (UI) zu erstellen. Um Steuerelemente und Fenster innerhalb des Kontexts einer Gruppe zu verschieben und zu verfolgen, bearbeiten Sie Ihre z-Reihenfolge. Die *z-Reihenfolge* ist das visuelle Schichten von Steuerelementen in einem Formular entlang der Z-Achse (Tiefe) des Formulars. Das Fenster oben in der z-Reihenfolge überlappt alle anderen Fenster. Alle anderen Fenster überlappen das Fenster am unteren Rand der z-Reihenfolge.

## <a name="to-layer-controls-at-design-time"></a>Auf ebenensteuerelemente zur Entwurfszeit

1. Wählen Sie ein Steuerelement aus, das Sie Ebenen möchten.

2. Zeigen Sie im Menü **Format** auf **Reihenfolge**, und klicken Sie dann auf **in den Vorder** Grund oder in den **Hintergrund**.

## <a name="to-layer-controls-programmatically"></a>Zum programmgesteuerten ebenensteuerelement

- Verwenden Sie <xref:System.Windows.Forms.Control.BringToFront%2A> die <xref:System.Windows.Forms.Control.SendToBack%2A> Methoden und, um die z-Reihenfolge der Steuerelemente zu bearbeiten.

     Wenn sich z. b <xref:System.Windows.Forms.TextBox> . ein `txtFirstName`Steuerelement,, unter einem anderen Steuerelement befindet und Sie es oben verwenden möchten, verwenden Sie den folgenden Code:

    ```vb
    txtFirstName.BringToFront()
    ```

    ```csharp
    txtFirstName.BringToFront();
    ```

    ```cpp
    txtFirstName->BringToFront();
    ```

> [!NOTE]
> Windows Forms unterstützt die Einschluss *Steuerung*. Die Einschluss Steuerung umfasst das Platzieren einer Reihe von Steuerelementen innerhalb eines enthaltenden Steuer Elements <xref:System.Windows.Forms.RadioButton> , z. <xref:System.Windows.Forms.GroupBox> b. eine Reihe von Steuerelementen in einem Steuerelement Anschließend können Sie die Steuerelemente innerhalb des enthaltenden Steuer Elements Schichten. Wenn Sie das Gruppenfeld verschieben, werden auch die Steuerelemente verschoben, da Sie darin enthalten sind.

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
