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
ms.openlocfilehash: 8d0abbf0f71ac176d17261a0ae863938c575bdaf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311651"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Vorgehensweise: Überlagern von Objekten in Windows Forms
Beim Erstellen einer komplexen Benutzeroberfläche, oder mit einem Formular der multiple Document Interface (MDI) arbeiten, sollten Sie häufig layer-Steuerelemente und untergeordnete Formulare komplexere Benutzeroberflächen (UI) erstellen. Zum Verschieben und das Verfolgen von Steuerelemente und Fenster innerhalb des Kontexts einer Gruppe, bearbeiten Sie die Z-Reihenfolge. *Z-Reihenfolge* ist die Schichtung der Steuerelemente in einem Formular entlang des Formulars z-Achse (Tiefe). Das Fenster am Anfang der Z-Reihenfolge überschneidet sich mit allen anderen Fenstern. Alle anderen Fenster überlappen, das Fenster am unteren Rand der Z-Reihenfolge.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-layer-controls-at-design-time"></a>Auf der Ebene von Steuerelementen zur Entwurfszeit  
  
1. Wählen Sie ein Steuerelement, das Sie überlagern möchten.  
  
2. Auf der **Format** Startmenü **Reihenfolge**, und klicken Sie dann auf **in den Vordergrund** oder **in den Hintergrund**.  
  
### <a name="to-layer-controls-programmatically"></a>Layer-Steuerelemente programmgesteuert  
  
-   Verwenden der <xref:System.Windows.Forms.Control.BringToFront%2A> und <xref:System.Windows.Forms.Control.SendToBack%2A> Methoden, um die Z-Anordnung der Steuerelemente ändern.  
  
     Z. B. wenn ein <xref:System.Windows.Forms.TextBox> Steuerelement `txtFirstName`, wird darunter ein anderes Steuerelement und Sie möchten im Vordergrund soll, verwenden Sie den folgenden Code:  
  
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
>  Windows Forms unterstützt *steuerelementkapselung*. Steuerelementkapselung umfasst eine Reihe von Steuerelementen in einem enthaltenden Steuerelement, z. B. eine Anzahl von platzieren <xref:System.Windows.Forms.RadioButton> -Steuerelementen innerhalb einer <xref:System.Windows.Forms.GroupBox> Steuerelement. Sie können dann die Steuerelemente innerhalb des enthaltenden Steuerelements zusätzliche. Die Steuerelemente, verschieben das Gruppenfeld verschoben werden, da sie darin enthalten sind.  
  
## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
