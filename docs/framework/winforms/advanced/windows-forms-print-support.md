---
title: Druckunterstützung in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 4ea04d0b6bb8ffa7182d5166ebd66b809adeed34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528553"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="a4019-102">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a4019-102">Windows Forms Print Support</span></span>
<span data-ttu-id="a4019-103">Beim Drucken in Windows Forms besteht im Wesentlichen aus mithilfe der [PrintDocument-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) -Komponente verwendet, damit der Benutzer das Drucken, und die [PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) Steuerelement [PrintDialog Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) und [PageSetupDialog-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) Komponenten zum Bereitstellen einer vertrauten grafischen Oberfläche für Benutzer, die daran gewöhnt, zu der Windows-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="a4019-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="a4019-104">Normalerweise erstellen Sie eine neue Instanz der der <xref:System.Drawing.Printing.PrintDocument> Komponente, legen Sie die Eigenschaften, die beschreiben, was gedruckt, mit der <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings> Klassen, und rufen die <xref:System.Drawing.Printing.PrintDocument.Print%2A> Methode, um das Dokument zu drucken.</span><span class="sxs-lookup"><span data-stu-id="a4019-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="a4019-105">Im Verlauf der Druck aus einer Windows-basierten Anwendung die <xref:System.Drawing.Printing.PrintDocument> Komponente wird ein Dialogfeld zum Drucken von Abort anzeigen, um Benutzer darauf aufmerksam die Tatsache, dass heraus drucken und ermöglichen den Druckauftrag abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="a4019-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4019-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a4019-106">In This Section</span></span>  
 [<span data-ttu-id="a4019-107">Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a4019-107">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="a4019-108">Erklärt, wie die <xref:System.Drawing.Printing.PrintDocument> Komponente zum Drucken aus einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a4019-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="a4019-109">Gewusst wie: Erfassen von Benutzereingaben in einem „PrintDialog“ zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a4019-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="a4019-110">Erläutert, wie so ändern Sie die ausgewählten Druckoptionen programmgesteuert mithilfe der <xref:System.Windows.Forms.PrintDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="a4019-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="a4019-111">Gewusst wie: Auswählen der einem Benutzercomputer zugewiesenen Drucker in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a4019-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="a4019-112">Beschreibt das Ändern der Drucker zum Drucken auf die Verwendung der <xref:System.Windows.Forms.PrintDialog> -Komponente zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a4019-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="a4019-113">Vorgehensweise: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a4019-113">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="a4019-114">Beschreibt, an den Drucker sendende von Grafiken.</span><span class="sxs-lookup"><span data-stu-id="a4019-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="a4019-115">Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a4019-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="a4019-116">Beschreibt, Senden von Text an den Drucker.</span><span class="sxs-lookup"><span data-stu-id="a4019-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="a4019-117">Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a4019-117">How to: Complete Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="a4019-118">Erläutert, wie Benutzer bis zum Abschluss eines Druckauftrags benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="a4019-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="a4019-119">Gewusst wie: Drucken eines Windows Form</span><span class="sxs-lookup"><span data-stu-id="a4019-119">How to: Print a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 <span data-ttu-id="a4019-120">Zeigt, wie eine Kopie des aktuellen Formulars gedruckt.</span><span class="sxs-lookup"><span data-stu-id="a4019-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="a4019-121">Gewusst wie: Drucken in Windows Forms unter Verwendung der Seitenansicht</span><span class="sxs-lookup"><span data-stu-id="a4019-121">How to: Print in Windows Forms Using Print Preview</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="a4019-122">Zeigt, wie eine <xref:System.Windows.Forms.PrintPreviewDialog> für das Drucken eines Dokuments.</span><span class="sxs-lookup"><span data-stu-id="a4019-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a4019-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a4019-123">Related Sections</span></span>  
 [<span data-ttu-id="a4019-124">PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="a4019-124">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="a4019-125">Erläutert die Verwendung des der <xref:System.Drawing.Printing.PrintDocument> Komponente.</span><span class="sxs-lookup"><span data-stu-id="a4019-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="a4019-126">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="a4019-126">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="a4019-127">Erläutert die Verwendung des der <xref:System.Windows.Forms.PrintDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="a4019-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="a4019-128">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a4019-128">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="a4019-129">Erläutert die Verwendung des der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a4019-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="a4019-130">PageSetupDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="a4019-130">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="a4019-131">Erläutert die Verwendung des der <xref:System.Windows.Forms.PageSetupDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="a4019-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="a4019-132">Beschreibt die Klassen in der <xref:System.Drawing.Printing> Namespace.</span><span class="sxs-lookup"><span data-stu-id="a4019-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
