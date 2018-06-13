---
title: Dokumentieren von Code mit XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: fa642adcfea9e80b41b5fc148df2b95b8fa44d88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650500"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="fc749-102">Dokumentieren von Code mit XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc749-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="fc749-103">Sie können den Code mithilfe von XML zu dokumentieren, in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc749-103">In Visual Basic, you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="fc749-104">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="fc749-104">XML Documentation Comments</span></span>  
 <span data-ttu-id="fc749-105">Visual Basic bietet eine einfache Möglichkeit zum automatischen Erstellen von XML-Dokumentation für Projekte.</span><span class="sxs-lookup"><span data-stu-id="fc749-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="fc749-106">Sie können automatisch generiert ein XML-Skelett für Ihre Typen und Member, und geben Sie dann für jeden Parameter und andere Hinweise Zusammenfassungen, beschreibende-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="fc749-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="fc749-107">Die XML-Dokumentation wird automatisch in eine XML-Datei mit dem gleichen Namen wie das Projekt und die Erweiterung ".xml" ausgegeben, mit der entsprechenden Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fc749-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="fc749-108">Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="fc749-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="fc749-109">Die XML-Datei kann verwendet werden oder anderweitige als XML.</span><span class="sxs-lookup"><span data-stu-id="fc749-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="fc749-110">Diese Datei befindet sich im gleichen Verzeichnis wie die Ausgabe .exe oder .dll-Datei des Projekts.</span><span class="sxs-lookup"><span data-stu-id="fc749-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="fc749-111">XML-Dokumentation beginnt mit `'''`.</span><span class="sxs-lookup"><span data-stu-id="fc749-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="fc749-112">Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="fc749-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="fc749-113">Die Dokumentation muss wohlgeformtes XML sein.</span><span class="sxs-lookup"><span data-stu-id="fc749-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="fc749-114">Wenn das XML nicht wohlgeformt ist, wird eine Warnung ausgegeben, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fc749-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="fc749-115">Entwickler können ihren eigenen Satz von Tags erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc749-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="fc749-116">Es ist ein empfohlene Satz von Tags (finden Sie in diesem Thema unter "Verwandte Abschnitte").</span><span class="sxs-lookup"><span data-stu-id="fc749-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="fc749-117">Einige der empfohlenen Tags haben eine besondere Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="fc749-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="fc749-118">Das \<param>-Tag wird verwendet, um Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fc749-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="fc749-119">Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fc749-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="fc749-120">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="fc749-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="fc749-121">Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fc749-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="fc749-122">Der Compiler stellt sicher, dass diese Codeelement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fc749-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="fc749-123">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="fc749-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="fc749-124">Der Compiler berücksichtigt auch alle `Imports` Anweisungen bei der Suche für einen Typ beschrieben, die der `cref` Attribut.</span><span class="sxs-lookup"><span data-stu-id="fc749-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="fc749-125">Die \<summary >-Tag wird von IntelliSense in Visual Studio verwendet, um weitere Informationen zu einem Typ oder Member anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fc749-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fc749-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="fc749-126">Related Sections</span></span>  
 <span data-ttu-id="fc749-127">Weitere Informationen zum Erstellen einer XML-Datei mit dem Dokumentationskommentare finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fc749-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="fc749-128">/doc</span><span class="sxs-lookup"><span data-stu-id="fc749-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="fc749-129">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="fc749-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="fc749-130">Verarbeiten der XML-Datei</span><span class="sxs-lookup"><span data-stu-id="fc749-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="fc749-131">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="fc749-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="fc749-132">XML-Tools in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fc749-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="fc749-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc749-133">See Also</span></span>  
 [<span data-ttu-id="fc749-134">Entwickeln von Anwendungen mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc749-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)  
 [<span data-ttu-id="fc749-135">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fc749-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
