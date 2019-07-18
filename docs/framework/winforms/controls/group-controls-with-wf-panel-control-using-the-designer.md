---
title: 'Vorgehensweise: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 662343af42f72816a5a673d2cd6d839a5dca9190
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971300"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Vorgehensweise: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer
Windows Forms <xref:System.Windows.Forms.Panel> Steuerelemente werden verwendet, um die Gruppierung anderer Steuerelemente. Es gibt drei Gründe zum Gruppieren von Steuerelementen. Eine ist die visuelle Gruppierung von verwandten Form-Elemente für eine übersichtliche Benutzeroberfläche. eine andere ist die programmgesteuerte Gruppieren von Optionsfeldern z. B. das letzte ist für die Steuerelemente zur Entwurfszeit als Einheit verschieben.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-group-of-controls"></a>Um eine Gruppe von Steuerelementen zu erstellen.  
  
1. Ziehen Sie eine <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Windows Forms** Registerkarte der Toolbox auf das Formular.  
  
2. Fügen Sie weitere Steuerelemente hinzu, um den Bereich, Zeichnen im Auswahlbereich.  
  
     Wenn Sie vorhandene Steuerelemente verfügen, die Sie in einem Panel schließen möchten, können Sie wählen alle Steuerelemente, verschieben Sie sie in die Zwischenablage, wählen Sie die <xref:System.Windows.Forms.Panel> steuern, und fügen Sie sie in den Bereich. Sie können auch in den Bereich ziehen.  
  
3. (Optional) Wenn Sie einen Rahmen um einen Bereich hinzufügen möchten, legen Sie dessen <xref:System.Windows.Forms.BorderStyle> Eigenschaft. Es gibt drei Optionen: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, und <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>Siehe auch

- [Panel-Steuerelement](panel-control-windows-forms.md)
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
- [Vorgehensweise: Festlegen des Hintergrunds eines Bereichs](how-to-set-the-background-of-a-windows-forms-panel.md)
