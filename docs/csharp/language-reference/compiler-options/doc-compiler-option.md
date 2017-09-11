---
title: -doc (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- FileProperties.BuildAction
- /doc
dev_langs:
- CSharp
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 58608c1301b2df3286c1f8a1de189f6256b19052
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="doc-c-compiler-options"></a><span data-ttu-id="00dd6-102">/doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="00dd6-102">/doc (C# Compiler Options)</span></span>
<span data-ttu-id="00dd6-103">Mit der Option **/doc** können Sie Dokumentationskommentare in eine XML-Datei einfügen.</span><span class="sxs-lookup"><span data-stu-id="00dd6-103">The **/doc** option allows you to place documentation comments in an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00dd6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00dd6-104">Syntax</span></span>  
  
```console  
/doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="00dd6-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="00dd6-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="00dd6-106">Die Ausgabedatei für XML, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="00dd6-106">The output file for XML, which is populated with the comments in the source code files of the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00dd6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00dd6-107">Remarks</span></span>  
 <span data-ttu-id="00dd6-108">In Quellcodedateien können Dokumentationskommentare, die Folgendem vorausgehen, verarbeitet und der XML-Datei hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="00dd6-108">In source code files, documentation comments that precede the following can be processed and added to the XML file:</span></span>  
  
-   <span data-ttu-id="00dd6-109">Benutzerdefinierte Typen wie eine [Klasse](../../../csharp/language-reference/keywords/class.md), ein [Delegat](../../../csharp/language-reference/keywords/delegate.md), oder eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md)</span><span class="sxs-lookup"><span data-stu-id="00dd6-109">Such user-defined types as a [class](../../../csharp/language-reference/keywords/class.md), [delegate](../../../csharp/language-reference/keywords/delegate.md), or [interface](../../../csharp/language-reference/keywords/interface.md)</span></span>  
  
-   <span data-ttu-id="00dd6-110">Member wie ein Feld, ein [Ereignis](../../../csharp/language-reference/keywords/event.md), eine [Eigenschaft](../../../csharp/programming-guide/classes-and-structs/using-properties.md), oder eine Methode</span><span class="sxs-lookup"><span data-stu-id="00dd6-110">Such members as a field, [event](../../../csharp/language-reference/keywords/event.md), [property](../../../csharp/programming-guide/classes-and-structs/using-properties.md), or method</span></span>  
  
 <span data-ttu-id="00dd6-111">Die Quellcodedatei, die Main enthält, wird zuerst in XML ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="00dd6-111">The source code file that contains Main is output first into the XML.</span></span>  
  
 <span data-ttu-id="00dd6-112">Lassen Sie den Dateinamen der XML-Datei mit der Assembly, die Sie unterstützen möchten, identisch sein, und stellen Sie sicher, dass sich die XML-Datei im gleichen Verzeichnis wie die Assembly befindet, um die generierte XML-Datei für die Verwendung mit der [IntelliSense](/visualstudio/ide/using-intellisense)-Funktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="00dd6-112">To use the generated .xml file for use with the [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the .xml file be the same as the assembly you want to support and then make sure the .xml file is in the same directory as the assembly.</span></span> <span data-ttu-id="00dd6-113">Demnach wird auch die XML-Datei gefunden, wenn im Visual Studio-Projekt auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00dd6-113">Thus, when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="00dd6-114">Weitere Informationen finden Sie unter [Anzeigen von XML-Codekommentaren](/visualstudio/ide/supplying-xml-code-comments).</span><span class="sxs-lookup"><span data-stu-id="00dd6-114">See [Supplying Code Comments](/visualstudio/ide/supplying-xml-code-comments) and for more information.</span></span>  
  
 <span data-ttu-id="00dd6-115">Wenn Sie nicht mit [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) kompilieren, wird `file` \<assembly>\</assembly>-Tags enthalten, die den Namen der Datei mit dem Assemblymanifest für die Ausgabedatei der Kompilierung angeben.</span><span class="sxs-lookup"><span data-stu-id="00dd6-115">Unless you compile with [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), `file` will contain \<assembly>\</assembly> tags specifying the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00dd6-116">Die Option „/doc“ gilt für alle Eingabedateien; oder, wenn sie in den Projekteinstellungen festgelegt wurde, für alle Dateien im Projekt.</span><span class="sxs-lookup"><span data-stu-id="00dd6-116">The /doc option applies to all input files; or, if set in the Project Settings, all files in the project.</span></span> <span data-ttu-id="00dd6-117">Verwenden Sie zum Deaktivieren von Warnungen im Zusammenhang mit Dokumentationskommentare für eine bestimmte Datei oder einen Codeabschnitt [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).</span><span class="sxs-lookup"><span data-stu-id="00dd6-117">To disable warnings related to documentation comments for a specific file or section of code, use [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).</span></span>  
  
 <span data-ttu-id="00dd6-118">Weitere Informationen für Methoden zum Generieren von Dokumentation aus Kommentaren in Ihrem Code finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).</span><span class="sxs-lookup"><span data-stu-id="00dd6-118">See [Recommended Tags for Documentation Comments](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="00dd6-119">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="00dd6-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="00dd6-120">Öffnen Sie die **Eigenschaften**-Seite des Projekts.</span><span class="sxs-lookup"><span data-stu-id="00dd6-120">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="00dd6-121">Klicken Sie auf die Registerkarte **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="00dd6-121">Click the **Build** tab.</span></span>  
  
3.  <span data-ttu-id="00dd6-122">Ändern Sie die Eigenschaft der **XML-Dokumentationsdatei**.</span><span class="sxs-lookup"><span data-stu-id="00dd6-122">Modify the **XML documentation file** property.</span></span>  
  
 <span data-ttu-id="00dd6-123">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="00dd6-123">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00dd6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00dd6-124">See Also</span></span>  
 <span data-ttu-id="00dd6-125">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="00dd6-125">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="00dd6-126">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="00dd6-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

