---
title: 'Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: cc352f15fb1e8b531cd0f9b298b2db4ce649d3cf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039646"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche mithilfe des Designers
In jedem Windows Form können Sie ein Steuerelement <xref:System.Windows.Forms.Button> als Schaltfläche "Abbrechen" festlegen. Wenn der Benutzer die ESC-Taste drückt, wird auf eine Schaltfläche Abbrechen geklickt, unabhängig davon, welches andere Steuerelement im Formular den Fokus besitzt. Eine solche Schaltfläche wird in der Regel so programmiert, dass der Benutzer schnell einen Vorgang beenden kann, ohne dass eine Aktion ausgeführt werden muss.

## <a name="to-designate-the-cancel-button"></a>So bestimmen Sie die Schaltfläche Abbrechen

1. Wählen Sie das Formular aus, in dem sich die Schaltfläche befindet.

2. Legen Sie im Fenster **Eigenschaften** die- <xref:System.Windows.Forms.Form.CancelButton%2A> Eigenschaft des Formulars auf den Namen des <xref:System.Windows.Forms.Button> -Steuer Elements fest.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Vorgehensweise: Antworten auf Windows Forms Schaltflächen Klicks](how-to-respond-to-windows-forms-button-clicks.md)
- [Vorgehensweise: Festlegen einer Windows Forms Schaltfläche als "annehmen"-Schaltfläche mithilfe des Designers](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Button-Steuerelement](button-control-windows-forms.md)
