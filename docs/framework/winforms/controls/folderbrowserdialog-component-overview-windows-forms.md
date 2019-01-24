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
ms.openlocfilehash: ce449937b89c686c868dcf337f46f1816d08d191
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717661"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="9354d-102">Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9354d-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="9354d-103">Die Windows-Formulare <xref:System.Windows.Forms.FolderBrowserDialog> Komponente ist ein modales Dialogfeld, das für das Durchsuchen und Auswählen von Ordnern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9354d-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="9354d-104">Neue Ordner können auch erstellt werden, innerhalb der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="9354d-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9354d-105">Verwenden Sie anstelle von Ordnern, Dateien auf den [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) Komponente.</span><span class="sxs-lookup"><span data-stu-id="9354d-105">To select files, instead of folders, use the [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="9354d-106">Die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente wird zur Laufzeit mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9354d-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="9354d-107">Legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> -Eigenschaft bestimmt den obersten Ordner und Unterordner, die in der Strukturansicht des Dialogfelds angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9354d-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="9354d-108">Nachdem Sie das Dialogfeld angezeigt wurde, können Sie mithilfe der <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Eigenschaft, um den Pfad des Ordners abzurufen, die ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="9354d-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="9354d-109">Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9354d-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9354d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9354d-110">See also</span></span>
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="9354d-111">Vorgehensweise: Wählen Sie Ordner mit der FolderBrowserDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9354d-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="9354d-112">FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="9354d-112">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
