---
title: Übersicht über die SaveFileDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: be5f70e2e8b0d5143ef387819689ce95564a72d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537446"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="071a5-102">Übersicht über die SaveFileDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="071a5-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="071a5-103">Die <xref:System.Windows.Forms.SaveFileDialog>-Komponente von Windows Forms ist ein vorkonfiguriertes Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="071a5-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="071a5-104">Es ist identisch mit dem Standard **Datei speichern** (Dialogfeld), die von Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="071a5-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="071a5-105">Die Vererbung erfolgt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="071a5-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="071a5-106">Arbeiten mit der SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="071a5-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="071a5-107">Verwenden Sie es als einfache Lösung für das Aktivieren von Benutzern zum Speichern von Dateien anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="071a5-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="071a5-108">Durch die Verwendung von auf Windows-Standarddialogfelder, ist die grundlegende Funktion der Anwendungen, die Sie erstellen, Benutzern sofort vertraut.</span><span class="sxs-lookup"><span data-stu-id="071a5-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="071a5-109">Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.SaveFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Speichern der Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="071a5-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="071a5-110">Sie können die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="071a5-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="071a5-111">Sie können eine Datei öffnen, im Modus "Lese-/Schreibzugriff" mithilfe der <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="071a5-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="071a5-112">Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.SaveFileDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="071a5-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071a5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="071a5-113">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="071a5-114">SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="071a5-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
