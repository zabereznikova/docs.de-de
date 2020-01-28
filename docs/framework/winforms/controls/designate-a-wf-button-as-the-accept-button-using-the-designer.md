---
title: Festlegen einer Schaltfläche als "annehmen"-Schaltfläche mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746064"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche mithilfe des Designers
In jedem Windows-Formular können Sie ein <xref:System.Windows.Forms.Button> Steuerelement als Accept-Schaltfläche festlegen, das auch als Standard Schaltfläche bezeichnet wird. Wenn der Benutzer die EINGABETASTE drückt, wird die Standard Schaltfläche unabhängig davon, welches andere Steuerelement im Formular den Fokus besitzt, angeklickt. Dies gilt auch, wenn das Steuerelement mit dem Fokus eine andere Schaltfläche ist – in diesem Fall wird auf die Schaltfläche mit dem Fokus geklickt – oder ein mehrzeilige Textfeld oder ein benutzerdefiniertes Steuerelement, das die EINGABETASTE fängt.

## <a name="to-designate-the-accept-button"></a>So bestimmen Sie die Accept-Schaltfläche

1. Wählen Sie das Formular aus, in dem sich die Schaltfläche befindet.

2. Legen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.Form.AcceptButton%2A>-Eigenschaft des Formulars auf den Namen des <xref:System.Windows.Forms.Button> Steuer Elements fest.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche mithilfe des Designers](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button-Steuerelement](button-control-windows-forms.md)
