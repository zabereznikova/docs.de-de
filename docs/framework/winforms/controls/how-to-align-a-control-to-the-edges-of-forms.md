---
title: 'Vorgehensweise: Ausrichten eines Steuerelements an Formularrändern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: 5d662489b7e31f391bbd508409e69c091a25592c
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015946"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a>Vorgehensweise: Ausrichten eines Steuerelements an Formularrändern

Sie können ein Steuerelement am Formularrand ausrichten, indem Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft festlegen. Diese Eigenschaft legt fest, wo auf dem Formular das Steuerelement sich befindet. Die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft kann auf einen der folgenden Werte festgelegt werden:

|Einstellung|Auswirkung auf das Steuerelement|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|Wird im unteren Bereich des Formulars angedockt.|
|<xref:System.Windows.Forms.DockStyle.Fill>|Füllt den gesamten verbleibenden Platz im Formular aus.|
|<xref:System.Windows.Forms.DockStyle.Left>|Wird an der linken Seite des Formulars angedockt.|
|<xref:System.Windows.Forms.DockStyle.None>|Wird nicht angedockt und wird an der mit der <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft angegebenen Position angezeigt.|
|<xref:System.Windows.Forms.DockStyle.Right>|Wird an der rechten Seite des Formulars angedockt.|
|<xref:System.Windows.Forms.DockStyle.Top>|Wird im oberen Bereich des Formulars angedockt.|

Diese Funktion wird zur Entwurfszeit in Visual Studio unterstützt.

## <a name="set-the-dock-property-for-your-control-at-run-time"></a>Festlegen der Dock-Eigenschaft für das Steuerelement zur Laufzeit

Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft im Code auf den geeigneten Wert fest.

```vb
' To set the Dock property internally.
Me.Dock = DockStyle.Top
' To set the Dock property from another object.
UserControl1.Dock = DockStyle.Top
```

```csharp
// To set the Dock property internally.
this.Dock = DockStyle.Top;
// To set the Dock property from another object.
UserControl1.Dock = DockStyle.Top;
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
- [Vorgehensweise: Verankern und Andocken untergeordneter Steuerelemente in einem FlowLayoutPanel-Steuerelement](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Vorgehensweise: Verankern und Andocken untergeordneter Steuerelemente in einem TableLayoutPanel-Steuerelement](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
