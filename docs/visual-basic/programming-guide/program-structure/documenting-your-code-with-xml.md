---
title: Dokumentieren von Code mit XML (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML, documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0ce3f216f9e851feb0b3506b6ed1279b7d9479e7
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="0d410-102">Dokumentieren von Code mit XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d410-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="0d410-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], Sie können den Code mit XML dokumentieren</span><span class="sxs-lookup"><span data-stu-id="0d410-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="0d410-104">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="0d410-104">XML Documentation Comments</span></span>  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0d410-105">bietet eine einfache Möglichkeit zum automatischen Erstellen von XML-Dokumentation für Projekte.</span><span class="sxs-lookup"><span data-stu-id="0d410-105"> provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="0d410-106">Sie können automatisch generiert ein XML-Skelett für Ihre Typen und Member und geben Sie dann für jeden Parameter und andere Hinweise Zusammenfassungen, beschreibende Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d410-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="0d410-107">Mit der entsprechenden Konfiguration wird die XML-Dokumentation automatisch in eine XML-Datei mit demselben Namen wie das Projekt und die Erweiterung ".xml" ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d410-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="0d410-108">Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="0d410-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="0d410-109">Die XML-Datei genutzt oder als XML bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0d410-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="0d410-110">Diese Datei befindet sich im gleichen Verzeichnis wie die Ausgabe .exe oder .dll-Datei des Projekts.</span><span class="sxs-lookup"><span data-stu-id="0d410-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="0d410-111">XML-Dokumentation beginnt mit `'''`.</span><span class="sxs-lookup"><span data-stu-id="0d410-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="0d410-112">Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="0d410-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="0d410-113">Die Dokumentation muss wohlgeformt sein XML.</span><span class="sxs-lookup"><span data-stu-id="0d410-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="0d410-114">Wenn das XML nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0d410-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="0d410-115">Entwickler können ihre eigenen Satz von Tags zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d410-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="0d410-116">Es gibt ein Reihe empfohlener Tags (siehe "Verwandte Abschnitte" in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="0d410-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="0d410-117">Einige der empfohlenen Tags haben eine besondere Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="0d410-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="0d410-118">Die \<Param > Tag wird verwendet, um Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="0d410-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="0d410-119">Wenn verwendet, stellt der Compiler sicher, dass der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0d410-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="0d410-120">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="0d410-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="0d410-121">Die `cref` Attribut angefügt werden kann, um alle Tags, um einen Verweis auf ein Codeelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0d410-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="0d410-122">Der Compiler überprüft, ob dieses Codeelement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0d410-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="0d410-123">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="0d410-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="0d410-124">Der Compiler berücksichtigt auch alle `Imports` Anweisungen, die bei der Suche für einen Typ, der gemäß der `cref` Attribut.</span><span class="sxs-lookup"><span data-stu-id="0d410-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="0d410-125">Die \<Zusammenfassung > Tag werden von IntelliSense im [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] zusätzliche Informationen über einen Typ oder Member angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d410-125">The \<summary> tag is used by IntelliSense in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0d410-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0d410-126">Related Sections</span></span>  
 <span data-ttu-id="0d410-127">Weitere Informationen zum Erstellen einer XML-Datei mit Dokumentationskommentaren finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="0d410-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="0d410-128">/doc</span><span class="sxs-lookup"><span data-stu-id="0d410-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="0d410-129">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="0d410-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="0d410-130">Verarbeiten der XML-Datei</span><span class="sxs-lookup"><span data-stu-id="0d410-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="0d410-131">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="0d410-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="0d410-132">XML-Tools in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0d410-132">XML Tools in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="0d410-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d410-133">See Also</span></span>  
 <span data-ttu-id="0d410-134">[Anwendungsentwicklung mit Visual Basic](../../../visual-basic/developing-apps/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d410-134">[Developing Applications with Visual Basic](../../../visual-basic/developing-apps/index.md) </span></span>  
<span data-ttu-id="0d410-135"> [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="0d410-135"> [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)</span></span>
