---
title: Erstellen eines Office Open-Quell-XML-Dokuments (C#)
description: Erstellen Sie in Microsoft Office ein XML-WordprocessingML-Dokument für die Verwendung im Zusammenhang mit C#-Tutorials. Für die Schritte in diesem Artikel wird Microsoft Office benötigt.
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: e6d6908ee6560218793454f3871705e74095f543
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103996"
---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="4cd03-104">Erstellen eines Office Open-Quell-XML-Dokuments (C#)</span><span class="sxs-lookup"><span data-stu-id="4cd03-104">Creating the Source Office Open XML Document (C#)</span></span>

<span data-ttu-id="4cd03-105">In diesem Thema wird das Erstellen des Office Open XML-WordprocessingML-Dokuments erläutert, das in den anderen Beispielen in diesem Lernprogramm verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4cd03-105">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="4cd03-106">Wenn Sie diese Anweisungen befolgen, entspricht Ihre Ausgabe der Ausgabe im jeweiligen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="4cd03-106">If you follow these instructions, your output will match the output provided in each example.</span></span>

<span data-ttu-id="4cd03-107">Die Beispiele in diesem Lernprogramm funktionieren mit jedem gültigen WordprocessingML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="4cd03-107">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>

<span data-ttu-id="4cd03-108">Um das in diesem Tutorial verwendete Dokument erstellen zu können, muss bei Ihnen entweder Microsoft Office 2007 oder höher oder Microsoft Office 2003 mit dem Compatibility Pack für Microsoft Office 2007-Dateiformate installiert sein.</span><span class="sxs-lookup"><span data-stu-id="4cd03-108">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="4cd03-109">Erstellen des WordprocessingML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="4cd03-109">Creating the WordprocessingML Document</span></span>

#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="4cd03-110">So erstellen Sie das WordprocessingML-Dokument</span><span class="sxs-lookup"><span data-stu-id="4cd03-110">To create the WordprocessingML document</span></span>

1. <span data-ttu-id="4cd03-111">Erstellen Sie ein neues Microsoft Word-Dokument.</span><span class="sxs-lookup"><span data-stu-id="4cd03-111">Create a new Microsoft Word document.</span></span>

2. <span data-ttu-id="4cd03-112">Fügen Sie in das neue Dokument den folgenden Text ein:</span><span class="sxs-lookup"><span data-stu-id="4cd03-112">Paste the following text into the new document:</span></span>

    ```text
    Parsing WordprocessingML with LINQ to XML

    The following example prints to the console.

    using System;

    class Program {
        public static void Main(string[] args) {
            Console.WriteLine("Hello World");
        }
    }

    This example produces the following output:

    Hello World
    ```

3. <span data-ttu-id="4cd03-113">Formatieren Sie die erste Zeile mit der Formatvorlage "Überschrift 1".</span><span class="sxs-lookup"><span data-stu-id="4cd03-113">Format the first line with the style "Heading 1".</span></span>

4. <span data-ttu-id="4cd03-114">Wählen Sie die Zeilen aus, die den C#-Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="4cd03-114">Select the lines that contain the C# code.</span></span> <span data-ttu-id="4cd03-115">Die erste Zeile beginnt mit dem `using`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4cd03-115">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="4cd03-116">Die letzte Zeile ist die letzte schließende geschweifte Klammer.</span><span class="sxs-lookup"><span data-stu-id="4cd03-116">The last line is the last closing brace.</span></span> <span data-ttu-id="4cd03-117">Formatieren Sie die Zeilen mit der Schriftart Courier.</span><span class="sxs-lookup"><span data-stu-id="4cd03-117">Format the lines with the courier font.</span></span> <span data-ttu-id="4cd03-118">Formatieren Sie sie anschließend mit einer neuen Formatvorlage, und geben Sie der neuen Formatvorlage den Namen "Code".</span><span class="sxs-lookup"><span data-stu-id="4cd03-118">Format them with a new style, and name the new style "Code".</span></span>

5. <span data-ttu-id="4cd03-119">Wählen Sie zum Schluss die gesamte Zeile aus, die die Ausgabe enthält, und formatieren Sie sie mit der `Code`-Formatvorlage.</span><span class="sxs-lookup"><span data-stu-id="4cd03-119">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>

6. <span data-ttu-id="4cd03-120">Speichern Sie das Dokument, und nennen Sie es <legacyBold>SampleDoc.docx</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="4cd03-120">Save the document, and name it SampleDoc.docx.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4cd03-121">Wenn Sie Microsoft Word 2003 verwenden, wählen Sie in der Dropdownliste **Dateityp** die Option **Word 2007-Dokument**.</span><span class="sxs-lookup"><span data-stu-id="4cd03-121">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>
