---
title: Übersicht über die PrintDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0b0e516364277133efc83e7324345ccea8328690
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535488"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="cf2d4-102">Übersicht über die PrintDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cf2d4-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="cf2d4-103">Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) Komponente ist ein vorkonfiguriertes Dialogfeld zum Auswählen eines Druckers, wählen die zu druckenden Seiten aus, und bestimmen weiterer druckbezogener Einstellungen in Windows-basierten Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-103">The Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="cf2d4-104">Verwenden Sie sie als einfache Lösung für die Auswahl von Druckern und druckbezogenen Einstellungen, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="cf2d4-105">Sie können Benutzern ermöglichen, verschiedene Teile ihrer Dokumente zu drucken: Alles drucken, Drucken ein ausgewählten Seitenbereichs oder Drucken einer Auswahl.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="cf2d4-106">Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="cf2d4-107">Die <xref:System.Windows.Forms.PrintDialog> Komponente erbt von der <xref:System.Windows.Forms.CommonDialog> Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="cf2d4-108">Arbeiten mit der Komponente</span><span class="sxs-lookup"><span data-stu-id="cf2d4-108">Working with the Component</span></span>  
 <span data-ttu-id="cf2d4-109">Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="cf2d4-110">Diese Komponente verfügt über Eigenschaften, die entweder einen einzelnen Druckauftrag beziehen (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder die Einstellungen von einem einzelnen Drucker (<xref:System.Drawing.Printing.PrinterSettings> Klasse).</span><span class="sxs-lookup"><span data-stu-id="cf2d4-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="cf2d4-111">Einer von beiden, kann wiederum mehrere Drucker freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="cf2d4-112">Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.PrintDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf2d4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf2d4-113">See Also</span></span>  
 <xref:System.Windows.Forms.PrintDialog>  
 [<span data-ttu-id="cf2d4-114">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="cf2d4-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
