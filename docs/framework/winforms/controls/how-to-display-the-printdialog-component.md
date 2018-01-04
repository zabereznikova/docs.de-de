---
title: 'Gewusst wie: Anzeigen der PrintDialog-Komponente'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d955febe528add4b774766a3b204f96eef5a119d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="40009-102">Gewusst wie: Anzeigen der PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="40009-102">How to: Display the PrintDialog Component</span></span>
<span data-ttu-id="40009-103">Die <xref:System.Windows.Forms.PrintDialog> Komponente ist der standard Windows-Dialogfeld "Drucken"-Feld, das viele Ihrer Benutzer vertraut werden.</span><span class="sxs-lookup"><span data-stu-id="40009-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="40009-104">Da Ihre Benutzer sofort mit der sie vertraut sind, wäre es auch hilfreich, für die Verwendung der <xref:System.Windows.Forms.PrintDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="40009-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
### <a name="to-display-the-printdialog-component"></a><span data-ttu-id="40009-105">So zeigen Sie die PrintDialog-Komponente an</span><span class="sxs-lookup"><span data-stu-id="40009-105">To display the PrintDialog component</span></span>  
  
-   <span data-ttu-id="40009-106">Rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> Methode innerhalb der Code Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="40009-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>  
  
     <span data-ttu-id="40009-107">Sobald die Komponente angezeigt wird, können die Benutzer damit interagieren und die Eigenschaften für den Druckauftrag einstellen.</span><span class="sxs-lookup"><span data-stu-id="40009-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="40009-108">Diese gespeichert sind, der <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` Klasse (und die <xref:System.Drawing.Printing.PageSettings> Klasse, wenn der Benutzer zugreift der [PageSetupDialog-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) über die <xref:System.Windows.Forms.PrintDialog> Komponente) mit dem Druckauftrag verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="40009-108">These are saved in the <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="40009-109">Dann können Sie Aufrufe an die von ihnen eingestellten Eigenschaften durchführen, um die spezifischen Merkmale des Druckauftrags anzugeben.</span><span class="sxs-lookup"><span data-stu-id="40009-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40009-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40009-110">See Also</span></span>  
 [<span data-ttu-id="40009-111">Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40009-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="40009-112">Gewusst wie: Erfassen von Benutzereingaben in einem „PrintDialog“ zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="40009-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [<span data-ttu-id="40009-113">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="40009-113">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="40009-114">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="40009-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [<span data-ttu-id="40009-115">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40009-115">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="40009-116">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="40009-116">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
