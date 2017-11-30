---
title: "Übersicht über die OpenFileDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35c947e3efbb9b2e5df775f83ffc6068e49c84e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="f6ed0-102">Übersicht über die OpenFileDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f6ed0-102">OpenFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="f6ed0-103">Bei der Windows Forms-Komponente <xref:System.Windows.Forms.OpenFileDialog> handelt es sich um ein vorkonfiguriertes Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="f6ed0-104">Er ist der gleiche **Dateiöffnungsmodus** (Dialogfeld), die von Windows-Betriebssystems verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="f6ed0-105">Die Vererbung erfolgt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="using-this-component"></a><span data-ttu-id="f6ed0-106">Verwenden diese Komponente</span><span class="sxs-lookup"><span data-stu-id="f6ed0-106">Using this Component</span></span>  
 <span data-ttu-id="f6ed0-107">Verwenden Sie diese Komponente in der Windows-basierten Anwendung als einfache Lösung für die Dateiauswahl anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="f6ed0-108">Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="f6ed0-109">Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.OpenFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Öffnen von Dateien schreiben.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>  
  
 <span data-ttu-id="f6ed0-110">Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="f6ed0-111">Sie können Benutzern mit mehreren Dateien geöffnet werden, ermöglichen die <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="f6ed0-112">Darüber hinaus können Sie die <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> Eigenschaft, um zu bestimmen, ob ein Kontrollkästchen schreibgeschützt sind und im Dialogfeld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="f6ed0-113">Die <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> Eigenschaft gibt an, ob das Kontrollkästchen "schreibgeschützt" ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="f6ed0-114">Schließlich die <xref:System.Windows.Forms.FileDialog.Filter%2A> Eigenschaft legt die aktuelle Filterzeichenfolge für den Namen fest, die im Feld "Dateien des Typs" im Dialogfeld angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>  
  
 <span data-ttu-id="f6ed0-115">Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.OpenFileDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6ed0-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ed0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6ed0-116">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="f6ed0-117">OpenFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="f6ed0-117">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
