---
title: Dokumentieren von Code mit XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 324519248b90d4f61e67803a10b3cd6c566a2a04
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404861"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="fde54-102">Dokumentieren von Code mit XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fde54-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="fde54-103">In Visual Basic können Sie Ihren Code mit XML dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="fde54-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="fde54-104">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="fde54-104">XML Documentation Comments</span></span>

<span data-ttu-id="fde54-105">Visual Basic bietet eine einfache Möglichkeit, automatisch eine XML-Dokumentation für-Projekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fde54-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="fde54-106">Sie können automatisch ein XML-Gerüst für Ihre Typen und Member generieren und dann Zusammenfassungen, eine beschreibende Dokumentation für jeden Parameter und andere Hinweise bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fde54-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="fde54-107">Beim entsprechenden Setup wird die XML-Dokumentation automatisch in eine XML-Datei mit dem gleichen Namen wie das Projekt und die XML-Erweiterung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="fde54-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="fde54-108">Weitere Informationen finden Sie unter [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="fde54-108">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="fde54-109">Die XML-Datei kann als XML-Datei verwendet oder anderweitig manipuliert werden.</span><span class="sxs-lookup"><span data-stu-id="fde54-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="fde54-110">Diese Datei befindet sich im gleichen Verzeichnis wie die EXE-Ausgabedatei oder die DLL-Datei Ihres Projekts.</span><span class="sxs-lookup"><span data-stu-id="fde54-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="fde54-111">Die XML-Dokumentation beginnt mit `'''` .</span><span class="sxs-lookup"><span data-stu-id="fde54-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="fde54-112">Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="fde54-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="fde54-113">Die Dokumentation muss wohlgeformtes XML sein.</span><span class="sxs-lookup"><span data-stu-id="fde54-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="fde54-114">Wenn die XML-Datei nicht wohl geformt ist, wird eine Warnung generiert, und die Dokumentations Datei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fde54-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="fde54-115">Entwickler können ihren eigenen Satz von Tags erstellen.</span><span class="sxs-lookup"><span data-stu-id="fde54-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="fde54-116">Es gibt einen empfohlenen Satz von Tags (siehe "Verwandte Abschnitte" in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="fde54-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="fde54-117">Einige der empfohlenen Tags haben eine besondere Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="fde54-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="fde54-118">Das- \<param> Tag wird verwendet, um Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fde54-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="fde54-119">Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fde54-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="fde54-120">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="fde54-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="fde54-121">Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fde54-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="fde54-122">Der Compiler überprüft, ob dieses Codeelement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fde54-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="fde54-123">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="fde54-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="fde54-124">Der Compiler respektiert auch alle-Anweisungen, wenn er nach `Imports` einem Typ sucht, der im-Attribut beschrieben wird `cref` .</span><span class="sxs-lookup"><span data-stu-id="fde54-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="fde54-125">Das- \<summary> Tag wird von IntelliSense in Visual Studio verwendet, um zusätzliche Informationen zu einem Typ oder Member anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fde54-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="fde54-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="fde54-126">Related Sections</span></span>

<span data-ttu-id="fde54-127">Ausführliche Informationen zum Erstellen einer XML-Datei mit Dokumentations Kommentaren finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fde54-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="fde54-128">-doc</span><span class="sxs-lookup"><span data-stu-id="fde54-128">-doc</span></span>](../../reference/command-line-compiler/doc.md)

- [<span data-ttu-id="fde54-129">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="fde54-129">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)

- [<span data-ttu-id="fde54-130">Verarbeiten der XML-Datei</span><span class="sxs-lookup"><span data-stu-id="fde54-130">Processing the XML File</span></span>](processing-the-xml-file.md)

- [<span data-ttu-id="fde54-131">Vorgehensweise: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="fde54-131">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)

- [<span data-ttu-id="fde54-132">XML-Tools in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fde54-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="fde54-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fde54-133">See also</span></span>

- [<span data-ttu-id="fde54-134">Entwickeln von Anwendungen mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fde54-134">Developing Applications with Visual Basic</span></span>](../../developing-apps/index.md)
- [<span data-ttu-id="fde54-135">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fde54-135">Visual Basic Programming Guide</span></span>](../index.md)
