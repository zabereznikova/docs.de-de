---
title: "Übersicht über das Panel-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8855c88a0ec60cd0d44d73046e44c9614347d90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="panel-control-overview-windows-forms"></a>Übersicht über das Panel-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.Panel> Steuerelemente werden verwendet, um eine erkennbare Gruppierung für andere Steuerelemente bereitstellen. In der Regel verwenden Sie Bereiche, um ein Formular von Funktion zu unterteilen. Sie möglicherweise z. B. ein Bestellformular, der angibt, mailing Optionen wie z. B. welche über Nacht Netzbetreiber verwenden. Gruppieren alle Optionen in einem Bereich erhält der Benutzer, einen logischen visuellen Hinweis auf. Zur Entwurfszeit Zeit alle Steuerelemente problemlos verschoben werden können: beim Verschieben der <xref:System.Windows.Forms.Panel> alle darin enthaltenen Steuerelemente zu verschieben, zu steuern. Die Steuerelemente in einem Bereich gruppiert durch zugegriffen werden können seine <xref:System.Windows.Forms.Control.Controls%2A> Eigenschaft. Diese Eigenschaft gibt eine Auflistung von <xref:System.Windows.Forms.Control> Instanzen, daher Sie in der Regel ein Steuerelement umgewandelt müssen abgerufen, auf diese Weise in den spezifischen Typ.  
  
## <a name="panel-versus-groupbox"></a>Panel im Vergleich zu GroupBox-Steuerelement  
 Die <xref:System.Windows.Forms.Panel> Steuerelement ähnelt der <xref:System.Windows.Forms.GroupBox> steuern; allerdings nur die <xref:System.Windows.Forms.Panel> Steuerelement Bildlaufleisten angezeigt werden, haben kann und nur die <xref:System.Windows.Forms.GroupBox> -Steuerelement zeigt eine Beschriftung.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Um die Bildlaufleisten anzuzeigen, legen Sie die <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> Eigenschaft `true`. Sie können auch die Darstellung des Bereichs anpassen, durch Festlegen der <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, und <xref:System.Windows.Forms.Panel.BorderStyle%2A> Eigenschaften. Weitere Informationen zu den <xref:System.Windows.Forms.Control.BackColor%2A> und <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaften finden Sie in [Vorgehensweise: Festlegen des Hintergrunds eines Bereichs](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md). Die <xref:System.Windows.Forms.Panel.BorderStyle%2A> Eigenschaft bestimmt, ob im Bereich mit keine sichtbaren Rahmen beschriebenen (<xref:System.Windows.Forms.BorderStyle.None>), eine einfache Zeile (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), oder die Zeile (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Panel>  
 [GroupBox-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)  
 [Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)  
 [Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
