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
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708131"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="b52a5-102">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b52a5-102">Windows Forms Print Support</span></span>
<span data-ttu-id="b52a5-103">Beim Drucken in Windows Forms besteht in erster Linie mit der [PrintDocument-Komponente](../controls/printdocument-component-windows-forms.md) Komponente, bei dem Benutzer ermöglichen, zu drucken, und die [PrintPreviewDialog-Steuerelement](../controls/printpreviewdialog-control-windows-forms.md) Steuerelement ["PrintDialog" Komponente](../controls/printdialog-component-windows-forms.md) und [PageSetupDialog-Komponente](../controls/pagesetupdialog-component-windows-forms.md) Komponenten eine vertraute grafische Oberfläche für Benutzer, die mit dem Windows-Betriebssystem vertraut zu sein.</span><span class="sxs-lookup"><span data-stu-id="b52a5-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="b52a5-104">Normalerweise erstellen Sie eine neue Instanz der der <xref:System.Drawing.Printing.PrintDocument> Komponente legen Sie die Eigenschaften, die beschreiben, was gedruckt, mit der <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings> Klassen, und rufen die <xref:System.Drawing.Printing.PrintDocument.Print%2A> Methode, um das Dokument zu drucken.</span><span class="sxs-lookup"><span data-stu-id="b52a5-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="b52a5-105">Im Verlauf der Druck aus einer Windows-basierten Anwendung die <xref:System.Drawing.Printing.PrintDocument> Komponente zeigt ein Dialogfeld abbrechen, um Benutzer auf die Tatsache, dass die Drucken stattfindet und den Druckauftrag abgebrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b52a5-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b52a5-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b52a5-106">In This Section</span></span>  
 [<span data-ttu-id="b52a5-107">Vorgehensweise: Erstellen von Druckaufträgen in Standard-Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b52a5-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="b52a5-108">Erläutert, wie die <xref:System.Drawing.Printing.PrintDocument> Komponente zum Drucken in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b52a5-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="b52a5-109">Vorgehensweise: Erfassen von Benutzereingaben in einem "PrintDialog" zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b52a5-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="b52a5-110">Erläutert, wie so ändern Sie die ausgewählten Druckoptionen programmgesteuert mithilfe der <xref:System.Windows.Forms.PrintDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b52a5-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="b52a5-111">Vorgehensweise: Auswählen der Drucker, die angefügt werden, auf dem Computer eines Benutzers in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b52a5-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="b52a5-112">Beschreibt das Ändern der Drucker zum Drucken auf mit der <xref:System.Windows.Forms.PrintDialog> -Komponente zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="b52a5-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="b52a5-113">Vorgehensweise: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b52a5-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="b52a5-114">Beschreibt, sendende von Grafiken an den Drucker.</span><span class="sxs-lookup"><span data-stu-id="b52a5-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="b52a5-115">Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b52a5-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="b52a5-116">Beschreibt senden Text an den Drucker.</span><span class="sxs-lookup"><span data-stu-id="b52a5-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="b52a5-117">Vorgehensweise: Vollständige Windows Forms-Druckaufträge</span><span class="sxs-lookup"><span data-stu-id="b52a5-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="b52a5-118">Erläutert, wie Benutzer bis zum Abschluss eines Druckauftrags benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="b52a5-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="b52a5-119">Vorgehensweise: Drucken eines Windows Form</span><span class="sxs-lookup"><span data-stu-id="b52a5-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="b52a5-120">Zeigt, wie eine Kopie des aktuellen Formulars gedruckt.</span><span class="sxs-lookup"><span data-stu-id="b52a5-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="b52a5-121">Vorgehensweise: Drucken Sie in Windows Forms unter Verwendung der Seitenansicht</span><span class="sxs-lookup"><span data-stu-id="b52a5-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="b52a5-122">Zeigt, wie eine <xref:System.Windows.Forms.PrintPreviewDialog> zum Drucken eines Dokuments.</span><span class="sxs-lookup"><span data-stu-id="b52a5-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b52a5-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b52a5-123">Related Sections</span></span>  
 [<span data-ttu-id="b52a5-124">PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="b52a5-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="b52a5-125">Erläutert die Verwendung des der <xref:System.Drawing.Printing.PrintDocument> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b52a5-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="b52a5-126">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b52a5-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="b52a5-127">Erläutert die Verwendung des der <xref:System.Windows.Forms.PrintDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b52a5-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="b52a5-128">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b52a5-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="b52a5-129">Erläutert die Verwendung des der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b52a5-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="b52a5-130">PageSetupDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b52a5-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="b52a5-131">Erläutert die Verwendung des der <xref:System.Windows.Forms.PageSetupDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b52a5-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="b52a5-132">Beschreibt die Klassen in der <xref:System.Drawing.Printing> Namespace.</span><span class="sxs-lookup"><span data-stu-id="b52a5-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
