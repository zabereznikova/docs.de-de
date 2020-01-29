---
title: Druckunterstützung
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732492"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="b3174-102">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3174-102">Windows Forms Print Support</span></span>
<span data-ttu-id="b3174-103">Das Drucken in Windows Forms besteht hauptsächlich aus der Verwendung der [PrintDocument-Komponenten](../controls/printdocument-component-windows-forms.md) Komponente, um dem Benutzer das Drucken zu ermöglichen, und dem [PrintPreviewDialog-Steuer](../controls/printpreviewdialog-control-windows-forms.md) Element-Steuerelement, der [PrintDialog-Komponente](../controls/printdialog-component-windows-forms.md) und den [PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) -Komponenten Komponenten, um Benutzern eine vertraute grafische Oberfläche bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="b3174-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="b3174-104">In der Regel erstellen Sie eine neue Instanz der <xref:System.Drawing.Printing.PrintDocument> Komponente, legen die Eigenschaften fest, die beschreiben, was mithilfe der Klassen <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings> gedruckt werden soll, und rufen die <xref:System.Drawing.Printing.PrintDocument.Print%2A>-Methode auf, um das Dokument tatsächlich zu drucken.</span><span class="sxs-lookup"><span data-stu-id="b3174-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="b3174-105">Während des Druckens aus einer Windows-basierten Anwendung zeigt die <xref:System.Drawing.Printing.PrintDocument> Komponente ein Dialogfeld zum Abbrechen des Abbruchs an, in dem Benutzer darauf aufmerksam gemacht werden, dass der Druckvorgang abgebrochen wird und der Druckauftrag abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3174-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3174-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b3174-106">In This Section</span></span>  
 [<span data-ttu-id="b3174-107">Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3174-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="b3174-108">Erläutert, wie die <xref:System.Drawing.Printing.PrintDocument> Komponente zum Drucken aus einem Windows Form verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3174-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="b3174-109">Gewusst wie: Erfassen von Benutzereingaben in einem „PrintDialog“ zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b3174-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="b3174-110">Erläutert, wie ausgewählte Druckoptionen Programm gesteuert mithilfe der <xref:System.Windows.Forms.PrintDialog> Komponente geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b3174-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="b3174-111">Gewusst wie: Auswählen der einem Benutzercomputer zugewiesenen Drucker in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3174-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="b3174-112">Beschreibt das Ändern des Druckers für das Drucken in mithilfe der <xref:System.Windows.Forms.PrintDialog> Komponente zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="b3174-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="b3174-113">Vorgehensweise: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3174-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="b3174-114">Beschreibt das Senden von Grafiken an den Drucker.</span><span class="sxs-lookup"><span data-stu-id="b3174-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="b3174-115">Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3174-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="b3174-116">Beschreibt das Senden von Text an den Drucker.</span><span class="sxs-lookup"><span data-stu-id="b3174-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="b3174-117">Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3174-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="b3174-118">Erläutert, wie Benutzer zur Beendigung eines Druckauftrags gewarnt werden.</span><span class="sxs-lookup"><span data-stu-id="b3174-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="b3174-119">Gewusst wie: Drucken eines Windows Form</span><span class="sxs-lookup"><span data-stu-id="b3174-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="b3174-120">Zeigt, wie eine Kopie des aktuellen Formulars gedruckt wird.</span><span class="sxs-lookup"><span data-stu-id="b3174-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="b3174-121">Gewusst wie: Drucken in Windows Forms unter Verwendung der Seitenansicht</span><span class="sxs-lookup"><span data-stu-id="b3174-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="b3174-122">Zeigt, wie ein <xref:System.Windows.Forms.PrintPreviewDialog> zum Drucken eines Dokuments verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3174-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b3174-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b3174-123">Related Sections</span></span>  
 [<span data-ttu-id="b3174-124">PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="b3174-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="b3174-125">Erläutert die Verwendung der <xref:System.Drawing.Printing.PrintDocument> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b3174-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="b3174-126">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b3174-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="b3174-127">Erläutert die Verwendung der <xref:System.Windows.Forms.PrintDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b3174-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="b3174-128">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b3174-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="b3174-129">Erläutert die Verwendung des <xref:System.Windows.Forms.PrintPreviewDialog>-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="b3174-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="b3174-130">PageSetupDialog Component</span><span class="sxs-lookup"><span data-stu-id="b3174-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="b3174-131">Erläutert die Verwendung der <xref:System.Windows.Forms.PageSetupDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b3174-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="b3174-132">Beschreibt die Klassen im <xref:System.Drawing.Printing>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="b3174-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
