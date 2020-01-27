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
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="4d322-102">Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4d322-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="4d322-103">Die Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> Komponente ist ein modales Dialogfeld, das zum Durchsuchen und Auswählen von Ordnern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4d322-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="4d322-104">Neue Ordner können auch aus der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4d322-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>

> [!NOTE]
> <span data-ttu-id="4d322-105">Verwenden Sie die [OpenFileDialog](openfiledialog-component-windows-forms.md) -Komponente, um Dateien anstelle von Ordnern auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4d322-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>

<span data-ttu-id="4d322-106">Die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente wird zur Laufzeit mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>-Methode angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d322-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="4d322-107">Legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>-Eigenschaft fest, um den obersten Ordner und alle Unterordner zu bestimmen, die in der Strukturansicht des Dialog Felds angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4d322-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="4d322-108">Sobald das Dialogfeld angezeigt wird, können Sie die <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>-Eigenschaft verwenden, um den Pfad des ausgewählten Ordners zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4d322-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>

<span data-ttu-id="4d322-109">Wenn Sie einem Formular hinzugefügt wird, wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d322-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d322-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d322-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="4d322-111">Gewusst wie: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d322-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="4d322-112">FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="4d322-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
