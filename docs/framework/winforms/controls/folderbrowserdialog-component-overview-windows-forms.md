---
title: Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: d08eb456ea2d2d3b805d3df7e0e79b26ea7d415e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708248"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.FolderBrowserDialog> Komponente ist ein modales Dialogfeld, das für das Durchsuchen und Auswählen von Ordnern verwendet wird. Neue Ordner können auch erstellt werden, innerhalb der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente.  
  
> [!NOTE]
>  Verwenden Sie anstelle von Ordnern, Dateien auf den [OpenFileDialog](openfiledialog-component-windows-forms.md) Komponente.  
  
 Die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente wird zur Laufzeit mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode. Legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> -Eigenschaft bestimmt den obersten Ordner und Unterordner, die in der Strukturansicht des Dialogfelds angezeigt werden. Nachdem Sie das Dialogfeld angezeigt wurde, können Sie mithilfe der <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Eigenschaft, um den Pfad des Ordners abzurufen, die ausgewählt wurde.  
  
 Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Vorgehensweise: Wählen Sie Ordner mit der FolderBrowserDialog-Komponente in Windows Forms](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [FolderBrowserDialog-Komponente](folderbrowserdialog-component-windows-forms.md)
