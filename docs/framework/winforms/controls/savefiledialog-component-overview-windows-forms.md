---
title: Übersicht über die SaveFileDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: ab8eb5409d017c6ea73a44e4e57ccec9cece4824
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631060"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="5e266-102">Übersicht über die SaveFileDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5e266-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="5e266-103">Die <xref:System.Windows.Forms.SaveFileDialog>-Komponente von Windows Forms ist ein vorkonfiguriertes Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="5e266-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="5e266-104">Dies entspricht dem als Standard **Datei speichern** Dialogfeld von Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e266-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="5e266-105">Die Vererbung erfolgt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="5e266-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="5e266-106">Arbeiten mit der SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="5e266-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="5e266-107">Verwenden Sie es als eine einfache Lösung zum Aktivieren von Benutzern zum Speichern von Dateien anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5e266-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="5e266-108">Auf Windows-Standarddialogfelder ist, die grundlegende Funktionalität von Anwendungen, die Sie erstellen Benutzern sofort vertraut.</span><span class="sxs-lookup"><span data-stu-id="5e266-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="5e266-109">Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.SaveFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Speichern von Dateien schreiben.</span><span class="sxs-lookup"><span data-stu-id="5e266-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="5e266-110">Sie können die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5e266-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="5e266-111">Öffnen Sie eine Datei im Lese-/Schreibzugriff mit der <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="5e266-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="5e266-112">Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.SaveFileDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5e266-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e266-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e266-113">See also</span></span>
- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="5e266-114">SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="5e266-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
