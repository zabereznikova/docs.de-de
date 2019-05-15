---
title: Vorgehensweise beim Anzeigen der PrintDialog-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637456"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="72086-102">Vorgehensweise beim Anzeigen der PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="72086-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="72086-103">Die <xref:System.Windows.Forms.PrintDialog> Komponente ist das standardmäßige Druckdialogfeld in Windows, das viele der Benutzer vertraut werden.</span><span class="sxs-lookup"><span data-stu-id="72086-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="72086-104">Da Ihre Benutzer sofort zurechtfinden werden, ist es wäre vorteilhaft für die Verwendung der <xref:System.Windows.Forms.PrintDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="72086-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="72086-105">So zeigen Sie die PrintDialog-Komponente an</span><span class="sxs-lookup"><span data-stu-id="72086-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="72086-106">Rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> innerhalb des Codes der Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="72086-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="72086-107">Sobald die Komponente angezeigt wird, können die Benutzer damit interagieren und die Eigenschaften für den Druckauftrag einstellen.</span><span class="sxs-lookup"><span data-stu-id="72086-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="72086-108">Diese werden gespeichert, der <xref:System.Drawing.Printing.PrinterSettings> Klasse (und die <xref:System.Drawing.Printing.PageSettings> Klasse, wenn der Benutzer greift auf die [PageSetupDialog-Komponente](pagesetupdialog-component-windows-forms.md) über die <xref:System.Windows.Forms.PrintDialog> Komponente) mit dem Druckauftrag verknüpften.</span><span class="sxs-lookup"><span data-stu-id="72086-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="72086-109">Dann können Sie Aufrufe an die von ihnen eingestellten Eigenschaften durchführen, um die spezifischen Merkmale des Druckauftrags anzugeben.</span><span class="sxs-lookup"><span data-stu-id="72086-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="72086-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72086-110">See also</span></span>

- [<span data-ttu-id="72086-111">Vorgehensweise: Erstellen von Druckaufträgen in Standard-Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72086-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="72086-112">Vorgehensweise: Erfassen von Benutzereingaben in einem "PrintDialog" zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="72086-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="72086-113">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="72086-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="72086-114">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="72086-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="72086-115">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72086-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="72086-116">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="72086-116">Windows Forms Controls</span></span>](index.md)
