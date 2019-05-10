---
title: 'Vorgehensweise: Anzeigen der kontextbezogenen Hilfe'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: bf3bcbff0cd6f3bbf71e96e748cb170d5ce68dfc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211398"
---
# <a name="how-to-display-pop-up-help"></a>Vorgehensweise: Kontextbezogene Hilfe anzeigen

Eine Möglichkeit zum Anzeigen von Hilfe in Windows Forms die **Hilfe** Schaltfläche auf der rechten Seite der Titelleiste, über die <xref:System.Windows.Forms.Form.HelpButton%2A> Eigenschaft. Diese Art, die Hilfe aufzurufen, eignet sich besonders für Dialogfelder. In modal (mit der <xref:System.Windows.Forms.Form.ShowDialog%2A>-Methode) angezeigten Dialogfeldern ist das Aufrufen externer Hilfesysteme problematisch, da modale Dialogfelder zuerst geschlossen werden müssen, ehe der Fokus auf ein anderes Fenster gerichtet werden kann. Außerdem ist die Verwendung der **Hilfe** Schaltfläche ist erforderlich, dass es ist keine **Minimieren** Schaltfläche oder **Maximieren** Schaltfläche in der Titelleiste angezeigt. Dies ist eine Konvention Dialogfelder, während der Formulare, die in der Regel über **Minimieren** und **Maximieren** Schaltflächen.

Sie können auch die <xref:System.Windows.Forms.HelpProvider> Komponente, um Steuerelemente auf Dateien in einem Hilfesystem verknüpfen, auch wenn Sie kontextbezogene Hilfe implementiert haben. Weitere Informationen finden Sie unter [Bereitstellen von Hilfeinformationen in einer Windows-Anwendung](how-to-provide-help-in-a-windows-application.md).

## <a name="display-pop-up-help"></a>Kontextbezogene Hilfe anzeigen

1. Ziehen Sie in Visual Studio eine [HelpProvider](../controls/helpprovider-component-windows-forms.md) -Komponente aus der Toolbox zu Ihrem Formular.

   Sie befindet sich in der Komponentenleiste im unteren Bereich des Windows Forms Designer.

2. Legen Sie im Fenster "Eigenschaften" die Eigenschaft <xref:System.Windows.Forms.Form.HelpButton%2A> auf `true` fest. Dadurch wird in der Titelleiste des Formulars auf der rechten Seite eine Schaltfläche mit einem Fragezeichen angezeigt.

3. Damit die Hilfeschaltfläche <xref:System.Windows.Forms.Form.HelpButton%2A> angezeigt werden kann, müssen Sie die Eigenschaften <xref:System.Windows.Forms.Form.MinimizeBox%2A> und <xref:System.Windows.Forms.Form.MaximizeBox%2A> des Formulars auf `false`, die Eigenschaft <xref:System.Windows.Forms.Form.ControlBox%2A> auf `true` und die Eigenschaft <xref:System.Windows.Forms.Form.FormBorderStyle%2A> auf einen der folgenden Werte festlegen: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> oder <xref:System.Windows.Forms.FormBorderStyle.Sizable>.

4. Wählen Sie das Steuerelement aus, für das Sie Hilfeinformationen in Ihrem Formular anzeigen möchten, und legen Sie im Fenster "Eigenschaften" den Hilfetext fest. Dies ist die Zeichenfolge mit Text, der in ein ähnliches Fenster angezeigt wird eine [QuickInfo](../controls/tooltip-component-windows-forms.md).

5. Drücken Sie **F5**.

6. Drücken Sie die **Hilfe** in der Titelleiste auf die Schaltfläche, und klicken Sie auf das Steuerelement auf dem Sie den Hilfetext festgelegt haben.

## <a name="see-also"></a>Siehe auch

- [Benutzerführung mithilfe von QuickInfos](control-help-using-tooltips.md)
- [Integrieren von Benutzerhilfe in Windows Forms](integrating-user-help-in-windows-forms.md)
- [Windows Forms](../index.md)
