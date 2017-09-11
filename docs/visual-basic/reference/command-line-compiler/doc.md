---
title: / doc | Microsoft-Dokumentation
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
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
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
ms.openlocfilehash: 974c41ba6ba4104a7fe17146390e14ccfbb7a521
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="doc"></a><span data-ttu-id="9c4a5-102">/doc</span><span class="sxs-lookup"><span data-stu-id="9c4a5-102">/doc</span></span>
<span data-ttu-id="9c4a5-103">Verarbeitet Dokumentationskommentare zu einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c4a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c4a5-104">Syntax</span></span>  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c4a5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9c4a5-105">Arguments</span></span>  
  
|<span data-ttu-id="9c4a5-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="9c4a5-106">Term</span></span>|<span data-ttu-id="9c4a5-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9c4a5-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="9c4a5-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9c4a5-108">`+` &#124; `-`</span></span>|<span data-ttu-id="9c4a5-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-109">Optional.</span></span> <span data-ttu-id="9c4a5-110">Angeben von +, oder nur `/doc`, generiert der Compiler Dokumentationsinformationen und platziert diese in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-110">Specifying +, or just `/doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="9c4a5-111">Angeben von `-` entspricht dem Angeben von nicht `/doc`, verursacht keine Dokumentationsinformationen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-111">Specifying `-` is the equivalent of not specifying `/doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="9c4a5-112">Erforderlich, wenn `/doc:` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-112">Required if `/doc:` is used.</span></span> <span data-ttu-id="9c4a5-113">Gibt die XML-Ausgabedatei, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="9c4a5-114">Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="9c4a5-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c4a5-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c4a5-115">Remarks</span></span>  
 <span data-ttu-id="9c4a5-116">Die `/doc` option steuert, ob der Compiler eine XML-Datei generiert, die die Dokumentationskommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-116">The `/doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="9c4a5-117">Bei Verwendung der `/doc:``file` Syntax der `file` Parameter gibt den Namen der XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-117">If you use the `/doc:``file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="9c4a5-118">Bei Verwendung von `/doc` oder `/doc+`, entnimmt der Compiler den Namen der XML-Datei der ausführbaren Datei oder Bibliothek, die die vom Compiler erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-118">If you use `/doc` or `/doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="9c4a5-119">Bei Verwendung von `/doc-` , oder geben Sie die `/doc` auswählen, erstellt der Compiler keine XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-119">If you use `/doc-` or do not specify the `/doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="9c4a5-120">In Quellcodedateien können Dokumentationskommentare den folgenden Definitionen vorausgehen:</span><span class="sxs-lookup"><span data-stu-id="9c4a5-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="9c4a5-121">Benutzerdefinierte Typen, z. B. ein [Klasse](../../../visual-basic/language-reference/statements/class-statement.md) oder [Schnittstelle](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="9c4a5-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="9c4a5-122">Member, z. B. ein Feld [Ereignis](../../../visual-basic/language-reference/statements/event-statement.md), [Eigenschaft](../../../visual-basic/language-reference/statements/property-statement.md), [Funktion](../../../visual-basic/language-reference/statements/function-statement.md), oder [Unterroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9c4a5-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="9c4a5-123">Verwenden Sie die generierte XML-Datei mit den [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] [IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) verfügen, können Sie den Dateinamen der XML-Datei der Assembly identisch sein, Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-123">To use the generated XML file with the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] [IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="9c4a5-124">Stellen Sie sicher, dass die XML-Datei im gleichen Verzeichnis wie die Assembly, damit bei der Assembly verwiesen wird die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] -Projekt die XML-Datei befindet sich ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] project, the .xml file is found as well.</span></span> <span data-ttu-id="9c4a5-125">XML-Dokumentationsdateien sind nicht erforderlich, damit IntelliSense funktioniert für Code in einem Projekt oder in Projekten, die von einem Projekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="9c4a5-126">Wenn Sie die Kompilierung mit `/target:module`, die XML-Datei enthält die Tags `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="9c4a5-127">Diese Tags Geben Sie den Namen der Datei, die das Assemblymanifest für die Ausgabedatei der Kompilierung enthält.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="9c4a5-128">Finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) für Methoden zum Generieren von Dokumentation aus Kommentaren im Code.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="9c4a5-129">Zum Festlegen von/doc in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="9c4a5-129">To set /doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="9c4a5-130">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9c4a5-131">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="9c4a5-132">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="9c4a5-132">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="9c4a5-133">2.  Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="9c4a5-134">3.  Legen Sie den Wert der **XML-Dokumentationsdatei generieren** Feld.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-134">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9c4a5-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c4a5-135">Example</span></span>  
 <span data-ttu-id="9c4a5-136">Finden Sie unter [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9c4a5-136">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4a5-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c4a5-137">See Also</span></span>  
 <span data-ttu-id="9c4a5-138">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c4a5-138">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="9c4a5-139"> [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)</span><span class="sxs-lookup"><span data-stu-id="9c4a5-139"> [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)</span></span>
