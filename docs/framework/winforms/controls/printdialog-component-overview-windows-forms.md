---
title: Übersicht über die PrintDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 4df3266cecd080d11d13af8d4678a5303fd669cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516926"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="912b4-102">Übersicht über die PrintDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="912b4-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="912b4-103">Die Windows-Formulare [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) Komponente ist ein vorkonfiguriertes Dialogfeld zum Auswählen eines Druckers, die zu druckenden Seiten auswählen sowie weitere druckbezogene Einstellungen in Windows-basierten Anwendungen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="912b4-103">The Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="912b4-104">Verwenden Sie sie als einfache Lösung für die Auswahl von Druckern und druckbezogenen Einstellungen, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="912b4-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="912b4-105">Sie können Benutzern ermöglichen, verschiedene Teile ihrer Dokumente zu drucken: Alles drucken, Drucken ein ausgewählten Seitenbereichs oder Drucken einer Auswahl.</span><span class="sxs-lookup"><span data-stu-id="912b4-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="912b4-106">Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="912b4-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="912b4-107">Die <xref:System.Windows.Forms.PrintDialog> Komponente erbt von der <xref:System.Windows.Forms.CommonDialog> Klasse.</span><span class="sxs-lookup"><span data-stu-id="912b4-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="912b4-108">Arbeiten mit der Komponente</span><span class="sxs-lookup"><span data-stu-id="912b4-108">Working with the Component</span></span>  
 <span data-ttu-id="912b4-109">Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="912b4-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="912b4-110">Diese Komponente verfügt über Eigenschaften, die sich auf einen einzelnen Druckauftrag beziehen (<xref:System.Drawing.Printing.PrintDocument> Klasse) oder die einen einzelnen Drucker (<xref:System.Drawing.Printing.PrinterSettings> Klasse).</span><span class="sxs-lookup"><span data-stu-id="912b4-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="912b4-111">Entweder diese kann wiederum mehrere Drucker freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="912b4-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="912b4-112">Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.PrintDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="912b4-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="912b4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="912b4-113">See also</span></span>
- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="912b4-114">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="912b4-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
