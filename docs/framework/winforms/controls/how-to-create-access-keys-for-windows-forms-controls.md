---
title: "Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af4cbcc5dacc4f9a0b5312b67838479bf6817228
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente
Ein *Zugriffsschlüssel* ist ein unterstrichenes Zeichen im Text eines Menüs, Menüelements oder die Bezeichnung eines Steuerelements, z. B. eine Schaltfläche. Mit einer Zugriffstaste kann der Benutzer "eine Schaltfläche klicken" durch Drücken der ALT-Taste in Kombination mit den vordefinierten Zugriffsschlüssel. Angenommen, eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausgeführt wird und daher seine `Text` auf "Drucken"-Eigenschaft festgelegt ist, ein kaufmännisches und-Zeichen hinzufügen, bevor der Buchstabe "P" den Buchstaben "P" in den Text der Schaltfläche unterstrichen werden, zur Laufzeit ausgelöst wird. Der Benutzer kann die Schaltfläche mit den durch Drücken von ALT + P zugeordneten Befehl ausführen. Sie keine Zugriffstaste für ein Steuerelement, die Fokus erhalten kann.  
  
### <a name="to-create-an-access-key-for-a-control"></a>So erstellen eine Zugriffstaste für ein Steuerelement  
  
1.  Legen Sie die `Text` Eigenschaft eine Zeichenfolge, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die die Verknüpfung werden.  
  
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
    >  Wenn Sie ein kaufmännisches und-Zeichen in eine Beschriftung einschließen möchten, ohne eine Zugriffstaste zu erstellen, enthalten zwei kaufmännische und-Zeichen (& &). Ein einzelnes kaufmännisches und-Zeichen in der Beschriftung angezeigt, und keine Zeichen sind unterstrichen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Button>  
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
