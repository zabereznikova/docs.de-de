---
title: Übersicht über das Panel-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 2b70996f7944f3f5ef8ef8bc80015836956a9b00
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715502"
---
# <a name="panel-control-overview-windows-forms"></a>Übersicht über das Panel-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.Panel> Steuerelemente werden verwendet, um eine erkennbare Gruppierung für andere Steuerelemente bereitzustellen. In der Regel verwenden Sie Bereiche unterteilen Sie eine Form von Funktion. Sie möglicherweise z. B. ein Bestellformular, der angibt, e-Mail-Optionen wie z. B. welche über Nacht Netzbetreiber verwenden. Gruppieren alle Optionen in einem Panel erhält der Benutzer, einen logische, visuellen Hinweis auf. Zur Entwurfszeit Zeit alle Steuerelemente problemlos verschoben werden können, beim Verschieben der <xref:System.Windows.Forms.Panel> alle darin enthaltenen Steuerelemente zu verschieben, zu steuern. Können Sie über die Steuerelemente in einem Panel gruppiert zugreifen seine <xref:System.Windows.Forms.Control.Controls%2A> Eigenschaft. Diese Eigenschaft gibt eine Auflistung von <xref:System.Windows.Forms.Control> Instanzen, weshalb Sie in der Regel werden ein Steuerelement umgewandelt abgerufen dadurch in den spezifischen Typ.  
  
## <a name="panel-versus-groupbox"></a>Bereich im Vergleich zu GroupBox-Steuerelement  
 Die <xref:System.Windows.Forms.Panel> -Steuerelement ähnelt der <xref:System.Windows.Forms.GroupBox> steuern; allerdings nur die <xref:System.Windows.Forms.Panel> Steuerelement kann die Bildlaufleisten angezeigt werden, haben und nur die <xref:System.Windows.Forms.GroupBox> Steuerelement über eine Beschriftung.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Legen Sie zum Anzeigen von Bildlaufleisten, die <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> Eigenschaft `true`. Sie können auch die Darstellung des Panels anpassen, durch Festlegen der <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, und <xref:System.Windows.Forms.Panel.BorderStyle%2A> Eigenschaften. Weitere Informationen zu den <xref:System.Windows.Forms.Control.BackColor%2A> und <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaften finden Sie [Vorgehensweise: Festlegen des Hintergrunds eines Bereichs](how-to-set-the-background-of-a-windows-forms-panel.md). Die <xref:System.Windows.Forms.Panel.BorderStyle%2A> Eigenschaft bestimmt, ob der Bereich mit keinen sichtbaren Rahmen beschrieben wird (<xref:System.Windows.Forms.BorderStyle.None>), eine einfache Linie (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), oder eine Zeile Shadowing durchgeführt wurde (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Panel>
- [GroupBox-Steuerelement](groupbox-control-windows-forms.md)
- [Vorgehensweise: Gruppieren von Steuerelementen mit dem Panel-Steuerelement in Windows Forms mithilfe des Designers](group-controls-with-wf-panel-control-using-the-designer.md)
- [Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
