---
title: Dokumentieren von Code mit XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 6b9fe9994b7bdf2259dcdb1ecef906e0f9955c8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59480624"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="6b858-102">Dokumentieren von Code mit XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b858-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="6b858-103">In Visual Basic können Sie den Code mit XML dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="6b858-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="6b858-104">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="6b858-104">XML Documentation Comments</span></span>

<span data-ttu-id="6b858-105">Visual Basic bietet eine einfache Möglichkeit zum automatischen Erstellen von XML-Dokumentation für Projekte.</span><span class="sxs-lookup"><span data-stu-id="6b858-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="6b858-106">Sie können eine XML-Grundgerüst für die verwendeten Typen und Member automatisch zu generieren und geben Sie dann für jeden Parameter und andere Hinweise Zusammenfassungen, aussagekräftigen-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b858-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="6b858-107">Die XML-Dokumentation wird automatisch in eine XML-Datei mit dem gleichen Namen wie das Projekt und der Erweiterung .xml ausgegeben, bei der entsprechenden Einrichtung.</span><span class="sxs-lookup"><span data-stu-id="6b858-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="6b858-108">Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="6b858-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="6b858-109">Die XML-Datei kann verbraucht oder im XML-Format bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="6b858-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="6b858-110">Diese Datei befindet sich im gleichen Verzeichnis wie die Ausgabe .exe oder .dll-Datei des Projekts.</span><span class="sxs-lookup"><span data-stu-id="6b858-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="6b858-111">XML-Dokumentation beginnt mit `'''`.</span><span class="sxs-lookup"><span data-stu-id="6b858-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="6b858-112">Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="6b858-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="6b858-113">Die Dokumentation muss wohlgeformtes XML sein.</span><span class="sxs-lookup"><span data-stu-id="6b858-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="6b858-114">Wenn der XML-Code nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6b858-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="6b858-115">Entwickler können ihren eigenen Satz von Tags erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b858-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="6b858-116">Es gibt ein Reihe empfohlener Tags (finden Sie in diesem Thema unter "Verwandte Abschnitte").</span><span class="sxs-lookup"><span data-stu-id="6b858-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="6b858-117">Einige der empfohlenen Tags haben eine besondere Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="6b858-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="6b858-118">Das \<param>-Tag wird verwendet, um Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6b858-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="6b858-119">Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6b858-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="6b858-120">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="6b858-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="6b858-121">Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6b858-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="6b858-122">Der Compiler überprüft, ob dieses Codeelement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6b858-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="6b858-123">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="6b858-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="6b858-124">Der Compiler berücksichtigt außerdem alle `Imports` Anweisungen, die bei der Suche für einen Typ beschrieben, die der `cref` Attribut.</span><span class="sxs-lookup"><span data-stu-id="6b858-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="6b858-125">Die \<summary >-Tag wird von IntelliSense in Visual Studio verwendet, um weitere Informationen über einen Typ oder Member anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6b858-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6b858-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6b858-126">Related Sections</span></span>

<span data-ttu-id="6b858-127">Ausführliche Informationen zum Erstellen einer XML-Datei mit Dokumentationskommentaren finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6b858-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="6b858-128">/doc</span><span class="sxs-lookup"><span data-stu-id="6b858-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)

- [<span data-ttu-id="6b858-129">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="6b858-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

- [<span data-ttu-id="6b858-130">Verarbeiten der XML-Datei</span><span class="sxs-lookup"><span data-stu-id="6b858-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [<span data-ttu-id="6b858-131">Vorgehensweise: Erstellen von XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="6b858-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [<span data-ttu-id="6b858-132">XML-Tools in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6b858-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="6b858-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b858-133">See also</span></span>

- [<span data-ttu-id="6b858-134">Entwickeln von Anwendungen mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b858-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
- [<span data-ttu-id="6b858-135">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6b858-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
