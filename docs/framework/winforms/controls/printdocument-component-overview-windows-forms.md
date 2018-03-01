---
title: "Übersicht über die PrintDocument-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 414a7972550558b40403b7f4cbfd9a49194666be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="5e6c9-102">Übersicht über die PrintDocument-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5e6c9-102">PrintDocument Component Overview (Windows Forms)</span></span>
<span data-ttu-id="5e6c9-103">Die Komponente [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) von Windows Forms wird verwendet, um die Eigenschaften festzulegen, die beschreiben, was gedruckt werden soll. Außerdem wird sie verwendet, um das Dokument in Windows-basierten Anwendungen drucken zu können.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-103">The Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="5e6c9-104">Sie kann zusammen mit der Komponente [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) verwendet werden, um alle Aspekte des Druckens eines Dokuments zu steuern.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-104">It can be used in conjunction with the [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>  
  
## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="5e6c9-105">Arbeiten mit der PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="5e6c9-105">Working with the PrintDocument Component</span></span>  
 <span data-ttu-id="5e6c9-106">Zwei der wichtigsten Szenarien, bei denen, die <xref:System.Drawing.Printing.PrintDocument> Komponente sind:</span><span class="sxs-lookup"><span data-stu-id="5e6c9-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>  
  
-   <span data-ttu-id="5e6c9-107">Einfache Druckaufträge wie das Drucken einer einzelnen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="5e6c9-108">In diesem Fall fügen Sie der <xref:System.Drawing.Printing.PrintDocument> Komponente auf einem Windows Form hinzufügen dann Programmierlogik, der ausgibt, eine Datei in der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="5e6c9-109">Die Programmierlogik muss mit der <xref:System.Drawing.Printing.PrintDocument.Print%2A> Methode, um das Dokument zu drucken.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="5e6c9-110">Diese Methode sendet eine <xref:System.Drawing.Graphics> in enthaltenes Objekt die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> Eigenschaft von der <xref:System.Drawing.Printing.PrintPageEventArgs> -Klasse, an den Drucker.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="5e6c9-111">Ein Beispiel, das so drucken Sie ein Textdokument mit veranschaulicht die <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5e6c9-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="5e6c9-112">Komplexere Druckaufträge, z.B. eine Situation, in der Sie bereits geschriebene Drucklogik wiederverwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="5e6c9-113">In einem solchen Fall leiten Sie eine neue Komponente aus der <xref:System.Drawing.Printing.PrintDocument> Komponente und überschreiben (finden Sie unter [überschreibt](~/docs/visual-basic/language-reference/modifiers/overrides.md) für Visual Basic oder [überschreiben](~/docs/csharp/language-reference/keywords/override.md) für c#) die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](~/docs/visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](~/docs/csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
 <span data-ttu-id="5e6c9-114">Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Drawing.Printing.PrintDocument> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5e6c9-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6c9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e6c9-115">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="5e6c9-116">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5e6c9-116">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="5e6c9-117">PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="5e6c9-117">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
