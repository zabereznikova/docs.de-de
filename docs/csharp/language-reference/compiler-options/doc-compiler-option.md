---
title: -doc (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: c46118a9b02df653844a0ca04f9e8f9952a957c4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333599"
---
# <a name="-doc-c-compiler-options"></a><span data-ttu-id="d0670-102">-doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="d0670-102">-doc (C# Compiler Options)</span></span>
<span data-ttu-id="d0670-103">Mit der Option **-doc** können Sie Dokumentationskommentare in eine XML-Datei einfügen.</span><span class="sxs-lookup"><span data-stu-id="d0670-103">The **-doc** option allows you to place documentation comments in an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0670-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0670-104">Syntax</span></span>  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d0670-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d0670-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="d0670-106">Die Ausgabedatei für XML, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="d0670-106">The output file for XML, which is populated with the comments in the source code files of the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0670-107">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="d0670-107">Remarks</span></span>  
 <span data-ttu-id="d0670-108">In Quellcodedateien können Dokumentationskommentare, die Folgendem vorausgehen, verarbeitet und der XML-Datei hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="d0670-108">In source code files, documentation comments that precede the following can be processed and added to the XML file:</span></span>  
  
-   <span data-ttu-id="d0670-109">Benutzerdefinierte Typen wie eine [Klasse](../../../csharp/language-reference/keywords/class.md), ein [Delegat](../../../csharp/language-reference/keywords/delegate.md), oder eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md)</span><span class="sxs-lookup"><span data-stu-id="d0670-109">Such user-defined types as a [class](../../../csharp/language-reference/keywords/class.md), [delegate](../../../csharp/language-reference/keywords/delegate.md), or [interface](../../../csharp/language-reference/keywords/interface.md)</span></span>  
  
-   <span data-ttu-id="d0670-110">Member wie ein Feld, ein [Ereignis](../../../csharp/language-reference/keywords/event.md), eine [Eigenschaft](../../../csharp/programming-guide/classes-and-structs/using-properties.md), oder eine Methode</span><span class="sxs-lookup"><span data-stu-id="d0670-110">Such members as a field, [event](../../../csharp/language-reference/keywords/event.md), [property](../../../csharp/programming-guide/classes-and-structs/using-properties.md), or method</span></span>  
  
 <span data-ttu-id="d0670-111">Die Quellcodedatei, die Main enthält, wird zuerst in XML ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="d0670-111">The source code file that contains Main is output first into the XML.</span></span>  
  
 <span data-ttu-id="d0670-112">Lassen Sie den Dateinamen der XML-Datei mit der Assembly, die Sie unterstützen möchten, identisch sein, und stellen Sie sicher, dass sich die XML-Datei im gleichen Verzeichnis wie die Assembly befindet, um die generierte XML-Datei für die Verwendung mit der [IntelliSense](/visualstudio/ide/using-intellisense)-Funktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0670-112">To use the generated .xml file for use with the [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the .xml file be the same as the assembly you want to support and then make sure the .xml file is in the same directory as the assembly.</span></span> <span data-ttu-id="d0670-113">Demnach wird auch die XML-Datei gefunden, wenn im Visual Studio-Projekt auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d0670-113">Thus, when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="d0670-114">Weitere Informationen finden Sie unter [Anzeigen von XML-Codekommentaren](/visualstudio/ide/supplying-xml-code-comments).</span><span class="sxs-lookup"><span data-stu-id="d0670-114">See [Supplying Code Comments](/visualstudio/ide/supplying-xml-code-comments) and for more information.</span></span>  
  
 <span data-ttu-id="d0670-115">Wenn Sie nicht mit [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) kompilieren, enthält `file` die Tags \<assembly>\</assembly>, die den Namen der Datei mit dem Assemblymanifest für die Ausgabedatei der Kompilierung angeben.</span><span class="sxs-lookup"><span data-stu-id="d0670-115">Unless you compile with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), `file` will contain \<assembly>\</assembly> tags specifying the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0670-116">Die Option „-doc“ gilt für alle Eingabedateien; oder, wenn sie in den Projekteinstellungen festgelegt wurde, für alle Dateien im Projekt.</span><span class="sxs-lookup"><span data-stu-id="d0670-116">The -doc option applies to all input files; or, if set in the Project Settings, all files in the project.</span></span> <span data-ttu-id="d0670-117">Verwenden Sie zum Deaktivieren von Warnungen im Zusammenhang mit Dokumentationskommentare für eine bestimmte Datei oder einen Codeabschnitt [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).</span><span class="sxs-lookup"><span data-stu-id="d0670-117">To disable warnings related to documentation comments for a specific file or section of code, use [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).</span></span>  
  
 <span data-ttu-id="d0670-118">Weitere Informationen für Methoden zum Generieren von Dokumentation aus Kommentaren in Ihrem Code finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).</span><span class="sxs-lookup"><span data-stu-id="d0670-118">See [Recommended Tags for Documentation Comments](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d0670-119">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="d0670-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="d0670-120">Öffnen Sie die **Eigenschaften**-Seite des Projekts.</span><span class="sxs-lookup"><span data-stu-id="d0670-120">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="d0670-121">Klicken Sie auf die Registerkarte **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d0670-121">Click the **Build** tab.</span></span>  
  
3. <span data-ttu-id="d0670-122">Ändern Sie die Eigenschaft der **XML-Dokumentationsdatei**.</span><span class="sxs-lookup"><span data-stu-id="d0670-122">Modify the **XML documentation file** property.</span></span>  
  
 <span data-ttu-id="d0670-123">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0670-123">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0670-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0670-124">See also</span></span>

- [<span data-ttu-id="d0670-125">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="d0670-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="d0670-126">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0670-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
