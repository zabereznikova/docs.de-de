---
title: 'Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: a0f567befb1e0c323dd16fffedec279ff836cbf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013217"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a>Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes mithilfe des Designers
Windows Forms-Steuerelemente zeigen in der Regel Text an, die für die primäre Funktion des Steuerelements zusammenhängt. Z. B. eine <xref:System.Windows.Forms.Button> Steuerelement in der Regel über eine Beschriftung, der angibt, welche Aktion ausgeführt wird, wenn die Schaltfläche geklickt wird. Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben. Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden.  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a>Die Text und die Schriftart mit dem Designer festlegen.  
  
1. Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft des Steuerelements in eine entsprechende Zeichenfolge.  
  
     Erstellen Sie eine unterstrichene Zugriffstaste, ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die die Tastenkombination.  
  
2. Klicken Sie im Fenster Eigenschaften auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft.  
  
     Wählen Sie im Dialogfeld Standardformen für Schriftarten die Schriftart, Schriftschnitt, Größe, Effekte (z. B. durchgestrichen oder unterstrichen) und Skripts, die Sie möchten.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Verwenden von Schriftarten und Text](../advanced/using-fonts-and-text.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
