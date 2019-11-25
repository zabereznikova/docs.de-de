---
title: Erstellen eines Office Open-Quell-XML-Dokuments
ms.date: 07/20/2015
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
ms.openlocfilehash: 5f7a9baebd2d1db73ab17924e0ff8a7408637ee8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346416"
---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a><span data-ttu-id="0c752-102">Creating the Source Office Open XML Document (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c752-102">Creating the Source Office Open XML Document (Visual Basic)</span></span>
<span data-ttu-id="0c752-103">In diesem Thema wird das Erstellen des Office Open XML-WordprocessingML-Dokuments erläutert, das in den anderen Beispielen in diesem Lernprogramm verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c752-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="0c752-104">Wenn Sie diese Anweisungen befolgen, entspricht Ihre Ausgabe der Ausgabe im jeweiligen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0c752-104">If you follow these instructions, your output will match the output provided in each example.</span></span>  
  
 <span data-ttu-id="0c752-105">Die Beispiele in diesem Lernprogramm funktionieren mit jedem gültigen WordprocessingML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="0c752-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>  
  
 <span data-ttu-id="0c752-106">Um das in diesem Tutorial verwendete Dokument erstellen zu können, muss bei Ihnen entweder Microsoft Office 2007 oder höher oder Microsoft Office 2003 mit dem Compatibility Pack für Microsoft Office 2007-Dateiformate installiert sein.</span><span class="sxs-lookup"><span data-stu-id="0c752-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="0c752-107">Erstellen des WordprocessingML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="0c752-107">Creating the WordprocessingML Document</span></span>  
  
#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="0c752-108">So erstellen Sie das WordprocessingML-Dokument</span><span class="sxs-lookup"><span data-stu-id="0c752-108">To create the WordprocessingML document</span></span>  
  
1. <span data-ttu-id="0c752-109">Erstellen Sie ein neues Microsoft Word-Dokument.</span><span class="sxs-lookup"><span data-stu-id="0c752-109">Create a new Microsoft Word document.</span></span>  
  
2. <span data-ttu-id="0c752-110">Fügen Sie in das neue Dokument den folgenden Text ein:</span><span class="sxs-lookup"><span data-stu-id="0c752-110">Paste the following text into the new document:</span></span>  
  
    ```text  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3. <span data-ttu-id="0c752-111">Formatieren Sie die erste Zeile mit der Formatvorlage "Überschrift 1".</span><span class="sxs-lookup"><span data-stu-id="0c752-111">Format the first line with the style "Heading 1".</span></span>  
  
4. <span data-ttu-id="0c752-112">Select the lines that contain the Visual Basic code.</span><span class="sxs-lookup"><span data-stu-id="0c752-112">Select the lines that contain the Visual Basic code.</span></span> <span data-ttu-id="0c752-113">Die erste Zeile beginnt mit dem `Imports`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="0c752-113">The first line starts with the `Imports` keyword.</span></span> <span data-ttu-id="0c752-114">The last line is "End Class".</span><span class="sxs-lookup"><span data-stu-id="0c752-114">The last line is "End Class".</span></span> <span data-ttu-id="0c752-115">Formatieren Sie die Zeilen mit der Schriftart Courier.</span><span class="sxs-lookup"><span data-stu-id="0c752-115">Format the lines with the courier font.</span></span> <span data-ttu-id="0c752-116">Formatieren Sie sie anschließend mit einer neuen Formatvorlage, und geben Sie der neuen Formatvorlage den Namen "Code".</span><span class="sxs-lookup"><span data-stu-id="0c752-116">Format them with a new style, and name the new style "Code".</span></span>  
  
5. <span data-ttu-id="0c752-117">Wählen Sie zum Schluss die gesamte Zeile aus, die die Ausgabe enthält, und formatieren Sie sie mit der `Code`-Formatvorlage.</span><span class="sxs-lookup"><span data-stu-id="0c752-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>  
  
6. <span data-ttu-id="0c752-118">Speichern Sie das Dokument, und nennen Sie es <legacyBold>SampleDoc.docx</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="0c752-118">Save the document, and name it SampleDoc.docx.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0c752-119">Wenn Sie Microsoft Word 2003 verwenden, wählen Sie in der Dropdownliste **Dateityp** die Option **Word 2007-Dokument**.</span><span class="sxs-lookup"><span data-stu-id="0c752-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c752-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c752-120">See also</span></span>

- [<span data-ttu-id="0c752-121">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c752-121">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
