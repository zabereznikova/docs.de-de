---
title: 'Gewusst wie: Sperren von Steuerelementen für Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: 8de22ae6667446620867f3c15aac3c4af65582bf
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423921"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Gewusst wie: Sperren von Steuerelementen für Windows Forms
Wenn Sie die Benutzeroberfläche (UI) Ihrer Windows-Anwendung entwerfen, können Sie die Steuerelemente sperren, sobald sie die richtige Position sind, damit Sie nicht versehentlich zu verschieben oder deren Größe ändern, wenn Sie andere Eigenschaften festlegen.  
  
 Darüber hinaus sperren und entsperren Sie alle Steuerelemente im Formular gleichzeitig angezeigt werden, die bei Formularen mit zahlreichen Steuerelementen hilfreich sind, oder Sie können einzelne Steuerelemente entsperren. Nachdem Sie alle Steuerelemente platziert haben, Sie möchten diese auf dem Formular, Sperren Sie diese um fehlerhafte Bewegung zu verhindern.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-lock-a-control"></a>Um ein Steuerelement zu sperren.  
  
1.  In der **Eigenschaften** Fenster, klicken Sie auf die **gesperrt** Eigenschaft, und wählen `true`. (Mit durch Doppelklicken auf den Namen wird die Einstellung der Eigenschaft.)  
  
     Alternativ klicken Sie auf das Steuerelement, und wählen Sie **Steuerelemente sperren**.  
  
    > [!NOTE]
    >  Steuerelemente Sperren verhindert werden, die auf eine neue Größe oder Position auf der Entwurfsoberfläche gezogen wird. Sie können jedoch weiterhin ändern die Größe oder Position der Steuerelemente von der **Eigenschaften** Fenster oder im Code.  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>Um alle Steuerelemente in einem Formular zu sperren.  
  
1.  Von der **Format** Menü wählen **Steuerelemente sperren**.  
  
    > [!NOTE]
    >  Mit diesem Befehl sperrt auch die Größe des Formulars auf, da ein Formular ein Steuerelement handelt.  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>Um alle gesperrten Steuerelemente in einem Formular zu entsperren.  
  
1.  Von der **Format** Menü wählen **Steuerelemente sperren**.  
  
     Alle zuvor gesperrten Steuerelemente im Formular sind jetzt entsperrt.  
  
### <a name="to-unlock-locked-controls-individually"></a>Um gesperrte Steuerelemente einzeln zu entsperren.  
  
1.  In der **Eigenschaften** Fenster, klicken Sie auf die **gesperrt** Eigenschaft, und wählen `false`. (Mit durch Doppelklicken auf den Namen wird die Einstellung der Eigenschaft.)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
