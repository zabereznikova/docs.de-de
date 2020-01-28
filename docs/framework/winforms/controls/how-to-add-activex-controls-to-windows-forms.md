---
title: ActiveX-Steuerelemente zu Formularen hinzufügen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 920c1111a5703352a4b624068e3d5ceae9892591
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746840"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Gewusst wie: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms

Während der Windows Forms-Designer in Visual Studio für das Hosten von Windows Forms Steuerelementen optimiert ist, können Sie auch ActiveX-Steuerelemente auf Windows Forms platzieren.

> [!CAUTION]
> Beim Hinzufügen von ActiveX-Steuerelementen sind Leistungseinschränkungen für Windows Forms vorhanden.

Vor dem Hinzufügen von ActiveX-Steuerelementen zum Formular müssen Sie Sie der Toolbox hinzufügen. Weitere Informationen finden Sie unter [com-Komponenten, Dialog Feld "Toolbox anpassen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))".

## <a name="add-an-activex-control-to-your-windows-form"></a>Hinzufügen eines ActiveX-Steuer Elements zu Windows Form

Um Ihrem Windows Form ein ActiveX-Steuerelement hinzuzufügen, doppelklicken Sie auf das-Steuerelement in der Toolbox.

Visual Studio fügt alle Verweise auf das-Steuerelement in Ihrem Projekt hinzu. Weitere Informationen zu den Punkten, die bei der Verwendung von ActiveX-Steuerelementen auf Windows Forms zu berücksichtigen sind, finden Sie unter [Überlegungen beim Hosting eines ActiveX-Steuer Elements in einem Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).

> [!NOTE]
> Das Windows Forms ActiveX-Steuerelement-Import Programm (Aximp. exe) erstellt Ereignis Argumente eines anderen Typs als erwartet beim Importieren von ActiveX-Dynamic Link Libraries. Die von "Aximp. exe" erstellten Argumente ähneln den folgenden: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, wenn `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` erwartet wird. Beachten Sie, dass diese Unregelmäßigkeiten nicht verhindern, dass Code normal funktioniert. Weitere Informationen finden Sie unter [Windows Forms ActiveX-Steuerelement-Import Programm (Aximp. exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [In zahlreichen Sprachen und Bibliotheken verglichene Steuerelemente und programmierbare Objekte](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
