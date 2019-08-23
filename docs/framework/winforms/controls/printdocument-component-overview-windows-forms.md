---
title: Übersicht über die PrintDocument-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 16a7f3a34ccb280f7bf91c52e29b20edc22130b9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928997"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="d6f08-102">Übersicht über die PrintDocument-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d6f08-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="d6f08-103">Die Komponente [PrintDocument](printdocument-component-windows-forms.md) von Windows Forms wird verwendet, um die Eigenschaften festzulegen, die beschreiben, was gedruckt werden soll. Außerdem wird sie verwendet, um das Dokument in Windows-basierten Anwendungen drucken zu können.</span><span class="sxs-lookup"><span data-stu-id="d6f08-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="d6f08-104">Sie kann zusammen mit der Komponente [PrintDialog](printdialog-component-windows-forms.md) verwendet werden, um alle Aspekte des Druckens eines Dokuments zu steuern.</span><span class="sxs-lookup"><span data-stu-id="d6f08-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="d6f08-105">Arbeiten mit der PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="d6f08-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="d6f08-106">Zwei der wichtigsten Szenarien, in denen die <xref:System.Drawing.Printing.PrintDocument> -Komponente enthalten ist, sind:</span><span class="sxs-lookup"><span data-stu-id="d6f08-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="d6f08-107">Einfache Druckaufträge wie das Drucken einer einzelnen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="d6f08-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="d6f08-108">In einem solchen Fall würden Sie die <xref:System.Drawing.Printing.PrintDocument> Komponente zu einem Windows Form hinzufügen und dann eine Programmierlogik hinzufügen, die eine Datei <xref:System.Drawing.Printing.PrintDocument.PrintPage> im-Ereignishandler ausgibt.</span><span class="sxs-lookup"><span data-stu-id="d6f08-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="d6f08-109">Die Programmierlogik sollte mit der <xref:System.Drawing.Printing.PrintDocument.Print%2A> -Methode zum Drucken des Dokuments in die-Methode münden.</span><span class="sxs-lookup"><span data-stu-id="d6f08-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="d6f08-110">Diese Methode sendet ein <xref:System.Drawing.Graphics> -Objekt, das in <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> der-Eigenschaft <xref:System.Drawing.Printing.PrintPageEventArgs> der-Klasse enthalten ist, an den Drucker.</span><span class="sxs-lookup"><span data-stu-id="d6f08-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="d6f08-111">Ein Beispiel für das Drucken eines Textdokuments mithilfe der <xref:System.Drawing.Printing.PrintDocument> -Komponente finden [Sie unter Gewusst wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d6f08-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="d6f08-112">Komplexere Druckaufträge, z.B. eine Situation, in der Sie bereits geschriebene Drucklogik wiederverwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d6f08-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="d6f08-113">In <xref:System.Drawing.Printing.PrintDocument> einem solchen Fall würden Sie eine neue Komponente von der Komponente ableiten und [über](../../../visual-basic/language-reference/modifiers/overrides.md) schreiben (siehe außer Kraft setzungen für Visual Basic oder C# <xref:System.Drawing.Printing.PrintDocument.PrintPage> [außer Kraft](../../../csharp/language-reference/keywords/override.md) setzung für) das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d6f08-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](../../../csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="d6f08-114">Wenn Sie einem Formular hinzugefügt wird, wird <xref:System.Drawing.Printing.PrintDocument> die Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6f08-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6f08-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6f08-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="d6f08-116">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d6f08-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="d6f08-117">PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="d6f08-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
