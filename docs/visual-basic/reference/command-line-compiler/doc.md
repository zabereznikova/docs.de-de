---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: 13005eb55b430f6ff9b3a6408582a02e53838742
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824584"
---
# <a name="-doc"></a><span data-ttu-id="d6189-102">-doc</span><span class="sxs-lookup"><span data-stu-id="d6189-102">-doc</span></span>
<span data-ttu-id="d6189-103">Verarbeitet Dokumentationskommentare zu einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="d6189-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6189-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6189-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6189-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d6189-105">Arguments</span></span>  
  
|<span data-ttu-id="d6189-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d6189-106">Term</span></span>|<span data-ttu-id="d6189-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d6189-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d6189-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d6189-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d6189-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d6189-109">Optional.</span></span> <span data-ttu-id="d6189-110">Ein Angeben von + oder einfach `-doc` veranlasst den Compiler, Dokumentationsinformationen zu generieren und diese in eine XML-Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="d6189-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="d6189-111">Ein Angeben von `-` entspricht dem Fehlen von `-doc`, sodass keine Dokumentationsinformationen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d6189-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="d6189-112">Erforderlich, wenn `-doc:` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6189-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="d6189-113">Gibt die XML-Ausgabedatei an, die mit den Kommentaren aus den Quellcodedateien der Kompilierung aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="d6189-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="d6189-114">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen (" ") setzen.</span><span class="sxs-lookup"><span data-stu-id="d6189-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6189-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6189-115">Remarks</span></span>  
 <span data-ttu-id="d6189-116">Die `-doc`-Option steuert, ob der Compiler eine XML-Datei generiert, die die Dokumentationskommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="d6189-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="d6189-117">Wenn Sie die `-doc:file`-Syntax verwenden, gibt der `file`-Parameter den Namen der XML-Datei an.</span><span class="sxs-lookup"><span data-stu-id="d6189-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="d6189-118">Wenn Sie `-doc` oder `-doc+` verwenden, übernimmt der Compiler den Namen der XML-Datei von der ausführbaren Datei oder Bibliothek, die vom Compiler erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d6189-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="d6189-119">Wenn Sie `-doc-` verwenden oder die `-doc`-Option nicht angeben, erstellt der Compiler keine XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="d6189-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="d6189-120">In Quellcodedateien können Dokumentationskommentare den folgenden Definitionen vorangestellt sein:</span><span class="sxs-lookup"><span data-stu-id="d6189-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="d6189-121">Benutzerdefinierte Typen wie [Class](../../../visual-basic/language-reference/statements/class-statement.md) und [Interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="d6189-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="d6189-122">Member, z. B. ein Feld, ein Ereignis ([Event](../../../visual-basic/language-reference/statements/event-statement.md)), eine Eigenschaft ([Property](../../../visual-basic/language-reference/statements/property-statement.md)), eine Funktion ([Function](../../../visual-basic/language-reference/statements/function-statement.md)) oder eine Unterroutine ([Sub](../../../visual-basic/language-reference/statements/sub-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="d6189-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="d6189-123">Wenn Sie die generierte XML-Datei mit der [IntelliSense](/visualstudio/ide/using-intellisense)-Funktionalität von Visual Studio verwenden möchten, geben Sie für die XML-Datei genau den Dateinamen an, den die Assembly hat, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="d6189-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="d6189-124">Stellen Sie sicher, dass sich die XML-Datei im selben Verzeichnis wie die Assembly befindet, sodass auch die XML-Datei gefunden wird, wenn im Visual Studio-Projekt auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d6189-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="d6189-125">XML-Dokumentationsdateien sind nicht erforderlich, damit IntelliSense für Code in einem Projekt oder in Projekten funktioniert, auf die in einem Projekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d6189-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="d6189-126">Sofern Sie nicht mit `/target:module` kompilieren, enthält die XML-Datei die Tags `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="d6189-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="d6189-127">Diese Tags geben den Namen der Datei an, die das Assemblymanifest für die Ausgabedatei der Kompilierung enthält.</span><span class="sxs-lookup"><span data-stu-id="d6189-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="d6189-128">Informationen zu den Möglichkeiten, wie Dokumentation aus Kommentaren in Ihrem Code generiert werden kann, finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md).</span><span class="sxs-lookup"><span data-stu-id="d6189-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="d6189-129">So legen Sie „-doc“ in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="d6189-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d6189-130">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d6189-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d6189-131">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d6189-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d6189-132">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="d6189-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d6189-133">3.  Legen Sie den Wert im Feld **XML-Dokumentationsdatei generieren** fest.</span><span class="sxs-lookup"><span data-stu-id="d6189-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d6189-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6189-134">Example</span></span>  
 <span data-ttu-id="d6189-135">Ein Beispiel finden Sie unter [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d6189-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6189-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6189-136">See also</span></span>

- [<span data-ttu-id="d6189-137">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d6189-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d6189-138">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="d6189-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
