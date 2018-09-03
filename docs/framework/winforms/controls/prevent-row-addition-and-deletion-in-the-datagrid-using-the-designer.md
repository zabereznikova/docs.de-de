---
title: 'Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: f138ab7a4906b1699f8fad029939dfe64f297a63
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485996"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Gelegentlich möchten Sie Benutzer daran hindern, neue Zeilen von Daten einzugeben oder vorhandene Zeilen in Ihrem <xref:System.Windows.Forms.DataGridView>-Steuerelement zu löschen. Neue Zeilen werden in die spezielle Zeile für neue Datensätze am unteren Rand des Steuerelements eingegeben. Wenn Sie Zeilen deaktivieren, wird die Zeile für neue Datensätze nicht angezeigt. Sie können dann das Steuerelement vollständig schreibgeschützt, durch das Deaktivieren der Zeile löschen und Bearbeiten der Zelle.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-prevent-row-addition-and-deletion"></a>Verhindern des Hinzufügens und Löschens  
  
-   Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und deaktivieren Sie die **hinzufügen aktivieren** und **löschen aktivieren** Kontrollkästchen.  
  
    > [!NOTE]
    >  Um das Steuerelement vollständig schreibgeschützt machen möchten, deaktivieren Sie die **Bearbeiten aktivieren** sowie das Kontrollkästchen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
