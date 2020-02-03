---
title: Übersicht über das Panel-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 3ea86e898e8a3e1ca90ba8e0a6240414702a1a73
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744316"
---
# <a name="panel-control-overview-windows-forms"></a>Übersicht über das Panel-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.Panel>-Steuerelemente werden verwendet, um eine identifizierbare Gruppierung für andere Steuerelemente bereitzustellen. In der Regel verwenden Sie Panels, um ein Formular nach Funktion zu unterteilen. Beispielsweise können Sie über ein Bestellformular verfügen, das Mailing Optionen angibt, z. b. den zu verwendenden Frachtunternehmen. Durch das Gruppieren aller Optionen in einem Panel erhält der Benutzer einen logischen visuellen Hinweis. Zur Entwurfszeit können alle Steuerelemente problemlos verschoben werden – wenn Sie das <xref:System.Windows.Forms.Panel> Steuerelement verschieben, werden auch alle darin enthaltenen Steuerelemente verschoben. Der Zugriff auf die in einem Panel gruppierten Steuerelemente kann über die <xref:System.Windows.Forms.Control.Controls%2A>-Eigenschaft erfolgen. Diese Eigenschaft gibt eine Auflistung von <xref:System.Windows.Forms.Control> Instanzen zurück, sodass Sie in der Regel ein Steuerelement, das auf diese Weise abgerufen wird, in den jeweiligen Typ umwandeln müssen.  
  
## <a name="panel-versus-groupbox"></a>Panel im Vergleich zu GroupBox  
 Das <xref:System.Windows.Forms.Panel> Steuerelement ähnelt dem <xref:System.Windows.Forms.GroupBox> Steuerelement; Allerdings kann nur das <xref:System.Windows.Forms.Panel> Steuerelement Scrollleisten aufweisen, und nur das <xref:System.Windows.Forms.GroupBox> Steuerelement zeigt eine Beschriftung an.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Um Bild Lauf leisten anzuzeigen, legen Sie die <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A>-Eigenschaft auf `true`fest. Sie können die Darstellung des Panels auch anpassen, indem Sie die Eigenschaften <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>und <xref:System.Windows.Forms.Panel.BorderStyle%2A> festlegen. Weitere Informationen zu den Eigenschaften <xref:System.Windows.Forms.Control.BackColor%2A> und <xref:System.Windows.Forms.Control.BackgroundImage%2A> finden Sie unter Gewusst [wie: Festlegen des Hintergrunds eines Panels](how-to-set-the-background-of-a-windows-forms-panel.md). Die <xref:System.Windows.Forms.Panel.BorderStyle%2A>-Eigenschaft bestimmt, ob der Bereich ohne sichtbaren Rahmen (<xref:System.Windows.Forms.BorderStyle.None>), eine einfache Linie (<xref:System.Windows.Forms.BorderStyle.FixedSingle>) oder eine Schatten Linie (<xref:System.Windows.Forms.BorderStyle.Fixed3D>) dargestellt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Panel>
- [GroupBox-Steuerelement](groupbox-control-windows-forms.md)
- [Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer](group-controls-with-wf-panel-control-using-the-designer.md)
- [Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
