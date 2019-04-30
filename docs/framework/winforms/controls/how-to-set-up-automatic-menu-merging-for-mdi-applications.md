---
title: 'Vorgehensweise: Einrichten des automatischem Zusammenführens von Menüs für MDI-Anwendungen (Multiple Document Interface)'
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 33e07bb655d81c6a802ebdce871a2fed845a5c96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013022"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Vorgehensweise: Einrichten des automatischem Zusammenführens von Menüs für MDI-Anwendungen (Multiple Document Interface)
Das folgende Verfahren bietet die grundlegenden Schritte zum Einrichten der automatischen Zusammenführen in einer Anwendung Multiple Document Interface (MDI) mit <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Zum Einrichten des automatischem Zusammenführens von  
  
1. Erstellen von übergeordneten MDI-Formulars durch Festlegen seiner <xref:System.Windows.Forms.Form.IsMdiContainer%2A> Eigenschaft `true`.  
  
2. Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> zum übergeordneten MDI-Fensters, Festlegen der <xref:System.Windows.Forms.Form.MainMenuStrip%2A> Eigenschaft mit dem <xref:System.Windows.Forms.MenuStrip>.  
  
3. Erstellen Sie ein untergeordnetes MDI-Formular, und legen dessen <xref:System.Windows.Forms.Form.MdiParent%2A> -Eigenschaft auf den Namen des übergeordneten Formulars.  
  
4. Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> , untergeordneten MDI-Formulars.  
  
5. Im untergeordneten Formular, legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft der <xref:System.Windows.Forms.MenuStrip> zu `false`.  
  
6. Hinzufügen von Menüelementen des untergeordneten Formulars <xref:System.Windows.Forms.MenuStrip> , die Sie mit des übergeordneten Formulars zusammenführen möchten <xref:System.Windows.Forms.MenuStrip> Wenn das untergeordnete Formular aktiviert ist.  
  
7. Verwenden der <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> Eigenschaft, die Sie im Menü des untergeordneten Formulars Elemente <xref:System.Windows.Forms.MenuStrip> steuern, wie sie mit dem übergeordneten Formular zusammenführen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
