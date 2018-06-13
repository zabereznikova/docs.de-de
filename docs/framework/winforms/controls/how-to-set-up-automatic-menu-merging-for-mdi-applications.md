---
title: 'Gewusst wie: Einrichten des automatischem Zusammenführens von Menüs für MDI-Anwendungen (Multiple Document Interface)'
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: e308ef8327fc439f52c4e3476a663f47fa00a379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533460"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Gewusst wie: Einrichten des automatischem Zusammenführens von Menüs für MDI-Anwendungen (Multiple Document Interface)
Das folgende Verfahren bietet die grundlegenden Schritte zum Einrichten der automatische Zusammenführung wird in einer Anwendung Multiple Document Interface (MDI) mit <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Zum Einrichten des automatischem Zusammenführens von Menüs  
  
1.  Erstellen von übergeordneten MDI-Formulars durch Festlegen seiner <xref:System.Windows.Forms.Form.IsMdiContainer%2A> Eigenschaft `true`.  
  
2.  Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> an das übergeordnete MDI-Element festlegen seiner <xref:System.Windows.Forms.Form.MainMenuStrip%2A> Eigenschaft mit <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Erstellen Sie ein untergeordnetes MDI-Formular, und legen seine <xref:System.Windows.Forms.Form.MdiParent%2A> -Eigenschaft auf den Namen des übergeordneten Formulars.  
  
4.  Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> zu untergeordneten MDI-Formulars.  
  
5.  Legen Sie auf dem Formular untergeordneten der <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft der <xref:System.Windows.Forms.MenuStrip> auf `false`.  
  
6.  Hinzufügen von Menüelementen des untergeordneten Formulars <xref:System.Windows.Forms.MenuStrip> , die Sie mit des übergeordneten Formulars zusammenführen möchten <xref:System.Windows.Forms.MenuStrip> Wenn das untergeordnete Formular aktiviert ist.  
  
7.  Verwenden der <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> -Eigenschaft der Elemente in des untergeordneten Formulars <xref:System.Windows.Forms.MenuStrip> steuern, wie sie mit dem übergeordneten Formular zusammenführen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
