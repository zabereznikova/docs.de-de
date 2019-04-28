---
title: 'Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: e6c829553163359301bad2cd896fc43562ee8069
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746816"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente
Ein *Zugriffsschlüssel* ist ein unterstrichenes Zeichen im Text eines Menüs, Menüelement oder die Bezeichnung eines Steuerelements wie einer Schaltfläche. Zusammen mit einer Zugriffstaste kann der Benutzer "eine Schaltfläche klicken Sie auf" durch Drücken der ALT-Taste in Kombination mit dem vordefinierten Zugriffsschlüssel. Angenommen, eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausführt und daher seine `Text` -Eigenschaftensatz auf "Print", ein kaufmännisches und-Zeichen vor der Buchstaben "P" den Buchstaben "P" in den Text der Schaltfläche unterstrichen werden, zur Laufzeit bewirkt, dass. Der Benutzer kann den Befehl mit der Schaltfläche durch Drücken von ALT + P verknüpften ausführen. Sie keine Zugriffstaste für ein Steuerelement, die keinen Fokus erhalten kann.  
  
### <a name="to-create-an-access-key-for-a-control"></a>Um einen Zugriffsschlüssel für ein Steuerelement zu erstellen.  
  
1. Legen Sie die `Text` Eigenschaft eine Zeichenfolge, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die die Verknüpfung werden.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  Wenn ein kaufmännisches und-Zeichen in einer Beschriftung einschließen möchten, ohne eine Tastenkombination erstellen, umfassen zwei kaufmännische und-Zeichen (& &). Ein einzelnes kaufmännisches und-Zeichen in der Beschriftung angezeigt, und es werden keine Zeichen unterstrichen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Button>
- [Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt](how-to-respond-to-windows-forms-button-clicks.md)
- [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
