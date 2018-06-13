---
title: 'Gewusst wie: Sperren von Steuerelementen für Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: f05da53f134f13bf5edbbe7ab8c5973f79bbca4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534744"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Gewusst wie: Sperren von Steuerelementen für Windows Forms
Wenn Sie die Benutzeroberfläche (UI) von der Windows-Anwendung entwerfen, können Sie die Steuerelemente sperren, sobald sie ordnungsgemäß positioniert sind, sodass Sie nicht versehentlich verschieben oder deren Größe ändern, wenn Sie andere Eigenschaften festlegen.  
  
 Darüber hinaus können Sie sperren und entsperren Sie alle Steuerelemente im Formular gleichzeitig, was für Formulare mit vielen Steuerelementen hilfreich ist, oder Sie einzelne Steuerelemente entsperren. Nachdem Sie alle Steuerelemente platziert haben, möchten Sie sie auf dem Formular, Sperren Sie diese um fehlerhafte Bewegung zu verhindern.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-lock-a-control"></a>So sperren Sie ein Steuerelement  
  
1.  In der **Eigenschaften** Fenster, klicken Sie auf die **gesperrt** Eigenschaft, und wählen `true`. (Doppelklicken auf den Namen wird die Einstellung der Eigenschaft.)  
  
     Alternativ können Sie mit der rechten Maustaste in des Steuerelements, und wählen Sie **Steuerelemente sperren**.  
  
    > [!NOTE]
    >  Sperren von Steuerelementen, die sie zu einer neuen Größe oder Position auf der Entwurfsoberfläche gezogenen verhindert. Sie können jedoch immer noch ändern die Größe oder Position von Steuerelementen mithilfe von der **Eigenschaften** Fenster oder im Code.  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>So sperren Sie alle Steuerelemente in einem Formular  
  
1.  Aus der **Format** Menü wählen **Steuerelemente sperren**.  
  
    > [!NOTE]
    >  Mit diesem Befehl wird auch die Größe des Formulars gesperrt, da ein Formular ein Steuerelement handelt.  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>Gesperrt, um alle Steuerelemente in einem Formular  
  
1.  Aus der **Format** Menü wählen **Steuerelemente sperren**.  
  
     Alle zuvor gesperrten Steuerelemente im Formular sind jetzt entsperrt.  
  
### <a name="to-unlock-locked-controls-individually"></a>Zum Entsperren Steuerelemente einzeln gesperrt werden  
  
1.  In der **Eigenschaften** Fenster, klicken Sie auf die **gesperrt** Eigenschaft, und wählen `false`. (Doppelklicken auf den Namen wird die Einstellung der Eigenschaft.)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
