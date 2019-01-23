---
title: 'Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente, die mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: e9524449b457fc276678ecaadd1d137e7280156a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527470"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente, die mithilfe des Designers
Ein *Zugriffsschlüssel* ist ein unterstrichenes Zeichen im Text eines Menüs, Menüelement oder die Bezeichnung eines Steuerelements wie einer Schaltfläche. Dadurch wird den Benutzer auf eine Schaltfläche "klicken", durch Drücken der ALT-Taste in Kombination mit dem vordefinierten Zugriffsschlüssel. Angenommen, eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausgeführt wird und daher seine `Text` -Eigenschaftensatz "Print", ein kaufmännisches und-Zeichen (&) vor dem Buchstaben "P" bewirkt, die Buchstaben "P dass" unterstrichen werden in den Text der Schaltfläche zur Laufzeit. Der Benutzer kann den Befehl mit der Schaltfläche durch Drücken von ALT + P verknüpften ausführen. Sie keine Zugriffstaste für ein Steuerelement, die keinen Fokus erhalten kann.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-access-key-for-a-control"></a>Um einen Zugriffsschlüssel für ein Steuerelement zu erstellen.  
  
1.  In der **Eigenschaften** legen die `Text` Eigenschaft eine Zeichenfolge, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die den Zugriffsschlüssel. Geben Sie den Buchstaben "P" als Zugriffstaste festlegen, z. B. **& Drucken** in das Raster.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Button>
- [Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
