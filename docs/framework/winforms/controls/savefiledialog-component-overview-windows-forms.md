---
title: "Übersicht über die SaveFileDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cbdc1cb96234e302458cbeac6d6ae26b63c956e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="b665d-102">Übersicht über die SaveFileDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b665d-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="b665d-103">Bei der Windows Forms-Komponente <xref:System.Windows.Forms.SaveFileDialog> handelt es sich um ein vorkonfiguriertes Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="b665d-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="b665d-104">Es ist identisch mit dem Standard **Datei speichern** (Dialogfeld), die von Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="b665d-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="b665d-105">Die Vererbung erfolgt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b665d-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="b665d-106">Arbeiten mit der SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b665d-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="b665d-107">Verwenden Sie es als einfache Lösung für das Aktivieren von Benutzern zum Speichern von Dateien anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b665d-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="b665d-108">Durch die Verwendung von auf Windows-Standarddialogfelder, ist die grundlegende Funktion der Anwendungen, die Sie erstellen, Benutzern sofort vertraut.</span><span class="sxs-lookup"><span data-stu-id="b665d-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="b665d-109">Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.SaveFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Speichern der Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="b665d-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="b665d-110">Sie können die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b665d-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="b665d-111">Sie können eine Datei öffnen, im Modus "Lese-/Schreibzugriff" mithilfe der <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b665d-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="b665d-112">Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.SaveFileDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b665d-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b665d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b665d-113">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="b665d-114">SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b665d-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
