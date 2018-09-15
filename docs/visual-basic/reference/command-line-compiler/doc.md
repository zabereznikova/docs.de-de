---
title: -Doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45638932"
---
# <a name="-doc"></a><span data-ttu-id="e5ceb-102">-Doc</span><span class="sxs-lookup"><span data-stu-id="e5ceb-102">-doc</span></span>
<span data-ttu-id="e5ceb-103">Verarbeitet Dokumentationskommentare zu einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ceb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5ceb-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e5ceb-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e5ceb-105">Arguments</span></span>  
  
|<span data-ttu-id="e5ceb-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e5ceb-106">Term</span></span>|<span data-ttu-id="e5ceb-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e5ceb-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="e5ceb-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e5ceb-108">`+` &#124; `-`</span></span>|<span data-ttu-id="e5ceb-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-109">Optional.</span></span> <span data-ttu-id="e5ceb-110">Angeben von +, oder nur `-doc`, generiert der Compiler generieren, und platzieren Sie es in eine XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="e5ceb-111">Angeben von `-` entspricht der Angabe nicht `-doc`, verursacht keine Dokumentationsinformationen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="e5ceb-112">Erforderlich, wenn `-doc:` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="e5ceb-113">Gibt die XML-Ausgabedatei, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="e5ceb-114">Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="e5ceb-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5ceb-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5ceb-115">Remarks</span></span>  
 <span data-ttu-id="e5ceb-116">Die `-doc` option steuert, ob der Compiler eine XML-Datei generiert, die die Dokumentationskommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="e5ceb-117">Bei Verwendung der `-doc:file` Syntax, die `file` Parameter gibt den Namen der XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="e5ceb-118">Bei Verwendung von `-doc` oder `-doc+`, nimmt der Compiler den Namen der XML-Datei aus der ausführbaren Datei oder Bibliothek, die die vom Compiler erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="e5ceb-119">Bei Verwendung von `-doc-` , oder geben Sie nicht die `-doc` auswählen, erstellt der Compiler keine XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="e5ceb-120">Dokumentationskommentare in Quellcodedateien, können die folgenden Definitionen voranstellen:</span><span class="sxs-lookup"><span data-stu-id="e5ceb-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="e5ceb-121">Benutzerdefinierte Typen, z. B. eine [Klasse](../../../visual-basic/language-reference/statements/class-statement.md) oder [Schnittstelle](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="e5ceb-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="e5ceb-122">Member, z. B. ein Feld, [Ereignis](../../../visual-basic/language-reference/statements/event-statement.md), [Eigenschaft](../../../visual-basic/language-reference/statements/property-statement.md), [Funktion](../../../visual-basic/language-reference/statements/function-statement.md), oder [Unterroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e5ceb-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="e5ceb-123">Verwenden Sie die generierte XML-Datei mit dem Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, können Sie den Dateinamen der XML-Datei der Assembly identisch sein, Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="e5ceb-124">Stellen Sie sicher, dass die XML-Datei im gleichen Verzeichnis wie die Assembly ist, wenn die Assembly in Visual Studio-Projekt verwiesen wird, sowie die XML-Datei gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="e5ceb-125">XML-Dokumentationsdateien sind nicht erforderlich, damit IntelliSense funktioniert für Code in einem Projekt oder innerhalb von Projekten, die von einem Projekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="e5ceb-126">Wenn Sie die Kompilierung mit `/target:module`, die XML-Datei enthält die Tags `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="e5ceb-127">Diese Tags Geben Sie den Namen der Datei mit dem Assemblymanifest für die Ausgabedatei der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="e5ceb-128">Finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md) Möglichkeiten zum Generieren von Dokumentation aus Kommentaren in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="e5ceb-129">Set - integriert Doc in Visual Studio-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="e5ceb-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e5ceb-130">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e5ceb-131">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e5ceb-132">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e5ceb-133">3.  Legen Sie den Wert der **XML-Dokumentationsdatei generieren** Feld.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e5ceb-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5ceb-134">Example</span></span>  
 <span data-ttu-id="e5ceb-135">Finden Sie unter [Documenting Your Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e5ceb-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ceb-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5ceb-136">See Also</span></span>  
 [<span data-ttu-id="e5ceb-137">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="e5ceb-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e5ceb-138">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="e5ceb-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
