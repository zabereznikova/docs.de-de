---
title: 'Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e89510558274558e560bf810afe746e250ff26a4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459232"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>Gewusst wie: Kopieren und Einfügen eines Element Host-Steuer Elements

In diesem Verfahren wird gezeigt, wie ein Windows Presentation Foundation (WPF)-Steuerelement in ein Windows Form in Visual Studio kopiert wird.

1. Fügen Sie in Visual Studio ein neues WPF-<xref:System.Windows.Controls.UserControl> zu einem Windows Forms Projekt hinzu. Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. Legen Sie im Fenster **Eigenschaften** den Wert des <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften von `UserControl1` auf **200**fest.

3. Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf **Blue**fest.

4. Erstellen Sie das Projekt.

5. Öffnen Sie `Form1` im Windows Forms-Designer.

6. Ziehen Sie aus der **Toolbox**eine Instanz von `UserControl1` auf das Formular.

   Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.

7. Wenn `elementHost1` ausgewählt ist, drücken Sie **STRG**+**C** , um Sie in die Zwischenablage zu kopieren.

8. Drücken Sie **STRG**+**V** , um das kopierte Steuerelement in das Formular einzufügen.

   Ein neues <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement mit dem Namen `elementHost2` wird auf dem Formular erstellt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
