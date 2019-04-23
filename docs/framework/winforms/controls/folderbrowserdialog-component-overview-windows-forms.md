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
ms.openlocfilehash: aae18167b29c71ad692cc6ba447457cd079374b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074130"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="b483b-102">Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b483b-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="b483b-103">Die Windows-Formulare <xref:System.Windows.Forms.FolderBrowserDialog> Komponente ist ein modales Dialogfeld, das für das Durchsuchen und Auswählen von Ordnern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b483b-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="b483b-104">Neue Ordner können auch erstellt werden, innerhalb der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b483b-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b483b-105">Verwenden Sie anstelle von Ordnern, Dateien auf den [OpenFileDialog](openfiledialog-component-windows-forms.md) Komponente.</span><span class="sxs-lookup"><span data-stu-id="b483b-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="b483b-106">Die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente wird zur Laufzeit mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b483b-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="b483b-107">Legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> -Eigenschaft bestimmt den obersten Ordner und Unterordner, die in der Strukturansicht des Dialogfelds angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b483b-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="b483b-108">Nachdem Sie das Dialogfeld angezeigt wurde, können Sie mithilfe der <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Eigenschaft, um den Pfad des Ordners abzurufen, die ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="b483b-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="b483b-109">Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b483b-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b483b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b483b-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="b483b-111">Vorgehensweise: Wählen Sie Ordner mit der FolderBrowserDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b483b-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="b483b-112">FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b483b-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
