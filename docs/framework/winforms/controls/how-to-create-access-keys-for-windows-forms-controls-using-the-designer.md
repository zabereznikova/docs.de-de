---
title: "Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed3bf2aa1e6081ca018f1b4dec98e6304a1aa95c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente mithilfe des Designers
Ein *Zugriffsschlüssel* ist ein unterstrichenes Zeichen im Text eines Menüs, Menüelements oder die Bezeichnung eines Steuerelements, z. B. eine Schaltfläche. Er ermöglicht es dem Benutzer eine Schaltfläche "auf", durch Drücken der ALT-Taste in Kombination mit den vordefinierten Zugriffsschlüssel. Angenommen, eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausgeführt wird und daher seine `Text` Eigenschaft "Print", Hinzufügen von ein kaufmännisches und-Zeichen (&) vor dem Buchstaben "P" bewirkt, der Buchstabe "P dass" unterstrichen werden in den Text der Schaltfläche zur Laufzeit festgelegt ist. Der Benutzer kann die Schaltfläche mit den durch Drücken von ALT + P zugeordneten Befehl ausführen. Sie keine Zugriffstaste für ein Steuerelement, die Fokus erhalten kann.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-access-key-for-a-control"></a>So erstellen eine Zugriffstaste für ein Steuerelement  
  
1.  In der **Eigenschaften** legen die `Text` Eigenschaft eine Zeichenfolge, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die den Zugriffsschlüssel werden. Geben Sie den Buchstaben "P" als Zugriffstaste festlegen, z. B. **& Drucken** in das Raster.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Button>  
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
