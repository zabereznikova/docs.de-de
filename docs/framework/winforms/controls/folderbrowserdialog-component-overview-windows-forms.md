---
title: Übersicht über die FolderBrowserDialog-Komponente
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745722"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)

Die Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> Komponente ist ein modales Dialogfeld, das zum Durchsuchen und Auswählen von Ordnern verwendet wird. Neue Ordner können auch aus der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente erstellt werden.

> [!NOTE]
> Verwenden Sie die [OpenFileDialog](openfiledialog-component-windows-forms.md) -Komponente, um Dateien anstelle von Ordnern auszuwählen.

Die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente wird zur Laufzeit mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>-Methode angezeigt. Legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>-Eigenschaft fest, um den obersten Ordner und alle Unterordner zu bestimmen, die in der Strukturansicht des Dialog Felds angezeigt werden. Sobald das Dialogfeld angezeigt wird, können Sie die <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>-Eigenschaft verwenden, um den Pfad des ausgewählten Ordners zu erhalten.

Wenn Sie einem Formular hinzugefügt wird, wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Gewusst wie: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [FolderBrowserDialog-Komponente](folderbrowserdialog-component-windows-forms.md)
