---
title: 'Gewusst wie: Überlagern von Objekten in Windows Forms'
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
ms.openlocfilehash: 1a2a25f2e7eaa6618c0bf535a34f7dc6a28d51fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Gewusst wie: Überlagern von Objekten in Windows Forms
Wenn Sie eine komplexe Benutzeroberfläche erstellen oder mit einem Formular der multiple Document Interface (MDI arbeiten), sollten Sie häufig überlagern Sie die Steuerelemente und untergeordnete Formulare komplexere Benutzeroberflächen (UI) zu erstellen. Zum Verschieben und das Verfolgen von Steuerelemente und Fenster innerhalb des Kontexts einer Gruppe, bearbeiten Sie ihre Z-Reihenfolge. *Z-Reihenfolge* ist die Schichtung der Steuerelemente in einem Formular auf das Formular z-Achse (Tiefe). Das Fenster am Anfang der Z-Reihenfolge überschneidet sich mit allen anderen Fenstern. Alle überlappen anderen Fenster am unteren Rand der Z-Reihenfolge.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-layer-controls-at-design-time"></a>Auf Ebene-Steuerelementen zur Entwurfszeit  
  
1.  Wählen Sie ein Steuerelement an die gewünschte Ebene.  
  
2.  Auf der **Format** Sie im Menü **Reihenfolge**, und klicken Sie dann auf **in den Vordergrund** oder **in den Hintergrund**.  
  
### <a name="to-layer-controls-programmatically"></a>Layer-Steuerelemente programmgesteuert  
  
-   Verwenden der <xref:System.Windows.Forms.Control.BringToFront%2A> und <xref:System.Windows.Forms.Control.SendToBack%2A> Methoden, um die Z-Reihenfolge der Steuerelemente zu bearbeiten.  
  
     Z. B. wenn ein <xref:System.Windows.Forms.TextBox> Steuerelement `txtFirstName`, wird unter einem anderen Steuerelement und möchten es im Vordergrund, verwenden Sie den folgenden Code:  
  
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
>  Windows Forms unterstützt *steuern Containment*. Steuerelementcontainern umfasst eine Reihe von Steuerelementen in einem enthaltenden Steuerelement, z. B. eine Anzahl von platzieren <xref:System.Windows.Forms.RadioButton> steuert innerhalb einer <xref:System.Windows.Forms.GroupBox> Steuerelement. Sie können dann die Steuerelemente innerhalb des enthaltenden Steuerelements Ebene. Das Gruppenfeld verschieben, die Steuerelemente auch, da sie darin enthalten sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
