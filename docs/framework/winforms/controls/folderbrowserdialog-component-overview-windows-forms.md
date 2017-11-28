---
title: "Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7fab1dbe01c5b21e510841b1541150f6152ab0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="bc09e-102">Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bc09e-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="bc09e-103">Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> Komponente ist ein modales Dialogfeld, das zum Durchsuchen und Auswählen von Ordnern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc09e-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="bc09e-104">Neuer Ordner können auch erstellt werden, in der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="bc09e-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc09e-105">Verwenden von Dateien, anstatt Ordner, der [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) Komponente.</span><span class="sxs-lookup"><span data-stu-id="bc09e-105">To select files, instead of folders, use the [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="bc09e-106">Die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente angezeigt wird, zur Laufzeit mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bc09e-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="bc09e-107">Legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> -Eigenschaft zum Bestimmen der oberste Ordner und alle Unterordner, die in der Strukturansicht des Dialogfelds angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bc09e-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="bc09e-108">Nachdem Sie das Dialogfeld angezeigt wurde, können Sie die <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Eigenschaft, um den Pfad des Ordners abzurufen, die ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="bc09e-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="bc09e-109">Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc09e-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc09e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc09e-110">See Also</span></span>  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [<span data-ttu-id="bc09e-111">Gewusst wie: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc09e-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [<span data-ttu-id="bc09e-112">FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="bc09e-112">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
