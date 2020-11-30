---
description: -doc (C#-Compileroptionen)
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
ms.openlocfilehash: b1d7fbbe98aaad16454fdd71c161f2a17a2f4f2e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91173255"
---
# <a name="-doc-c-compiler-options"></a><span data-ttu-id="7c6f1-103">-doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="7c6f1-103">-doc (C# Compiler Options)</span></span>

<span data-ttu-id="7c6f1-104">Mit der Option **-doc** können Sie Dokumentationskommentare in eine XML-Datei einfügen.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-104">The **-doc** option allows you to place documentation comments in an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6f1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c6f1-105">Syntax</span></span>  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="7c6f1-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="7c6f1-106">Arguments</span></span>  

 `file`  
 <span data-ttu-id="7c6f1-107">Die Ausgabedatei für XML, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-107">The output file for XML, which is populated with the comments in the source code files of the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c6f1-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7c6f1-108">Remarks</span></span>  

 <span data-ttu-id="7c6f1-109">In Quellcodedateien können Dokumentationskommentare, die Folgendem vorausgehen, verarbeitet und der XML-Datei hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="7c6f1-109">In source code files, documentation comments that precede the following can be processed and added to the XML file:</span></span>  
  
- <span data-ttu-id="7c6f1-110">Benutzerdefinierte Typen wie eine [Klasse](../keywords/class.md), ein [Delegat](../builtin-types/reference-types.md#the-delegate-type), oder eine [Schnittstelle](../keywords/interface.md)</span><span class="sxs-lookup"><span data-stu-id="7c6f1-110">Such user-defined types as a [class](../keywords/class.md), [delegate](../builtin-types/reference-types.md#the-delegate-type), or [interface](../keywords/interface.md)</span></span>  
  
- <span data-ttu-id="7c6f1-111">Member wie ein Feld, ein [Ereignis](../keywords/event.md), eine [Eigenschaft](../../programming-guide/classes-and-structs/using-properties.md), oder eine Methode</span><span class="sxs-lookup"><span data-stu-id="7c6f1-111">Such members as a field, [event](../keywords/event.md), [property](../../programming-guide/classes-and-structs/using-properties.md), or method</span></span>  
  
 <span data-ttu-id="7c6f1-112">Die Quellcodedatei, die Main enthält, wird zuerst in XML ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-112">The source code file that contains Main is output first into the XML.</span></span>  
  
 <span data-ttu-id="7c6f1-113">Lassen Sie den Dateinamen der XML-Datei mit der Assembly, die Sie unterstützen möchten, identisch sein, und stellen Sie sicher, dass sich die XML-Datei im gleichen Verzeichnis wie die Assembly befindet, um die generierte XML-Datei für die Verwendung mit der [IntelliSense](/visualstudio/ide/using-intellisense)-Funktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-113">To use the generated .xml file for use with the [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the .xml file be the same as the assembly you want to support and then make sure the .xml file is in the same directory as the assembly.</span></span> <span data-ttu-id="7c6f1-114">Demnach wird auch die XML-Datei gefunden, wenn im Visual Studio-Projekt auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-114">Thus, when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="7c6f1-115">Weitere Informationen finden Sie unter [Anzeigen von XML-Codekommentaren](/visualstudio/ide/reference/generate-xml-documentation-comments).</span><span class="sxs-lookup"><span data-stu-id="7c6f1-115">See [Supplying Code Comments](/visualstudio/ide/reference/generate-xml-documentation-comments) and for more information.</span></span>  
  
 <span data-ttu-id="7c6f1-116">Wenn Sie nicht mit [-target:module](./target-module-compiler-option.md) kompilieren, enthält `file` die Tags \<assembly>\</assembly>, die den Namen der Datei mit dem Assemblymanifest für die Ausgabedatei der Kompilierung angeben.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-116">Unless you compile with [-target:module](./target-module-compiler-option.md), `file` will contain \<assembly>\</assembly> tags specifying the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c6f1-117">Die Option „-doc“ gilt für alle Eingabedateien; oder, wenn sie in den Projekteinstellungen festgelegt wurde, für alle Dateien im Projekt.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-117">The -doc option applies to all input files; or, if set in the Project Settings, all files in the project.</span></span> <span data-ttu-id="7c6f1-118">Verwenden Sie zum Deaktivieren von Warnungen im Zusammenhang mit Dokumentationskommentare für eine bestimmte Datei oder einen Codeabschnitt [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span><span class="sxs-lookup"><span data-stu-id="7c6f1-118">To disable warnings related to documentation comments for a specific file or section of code, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span></span>  
  
 <span data-ttu-id="7c6f1-119">Weitere Informationen für Methoden zum Generieren von Dokumentation aus Kommentaren in Ihrem Code finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).</span><span class="sxs-lookup"><span data-stu-id="7c6f1-119">See [Recommended Tags for Documentation Comments](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="7c6f1-120">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="7c6f1-120">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="7c6f1-121">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-121">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="7c6f1-122">Klicken Sie auf die Registerkarte **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-122">Click the **Build** tab.</span></span>  
  
3. <span data-ttu-id="7c6f1-123">Ändern Sie die Eigenschaft der **XML-Dokumentationsdatei**.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-123">Modify the **XML documentation file** property.</span></span>  
  
 <span data-ttu-id="7c6f1-124">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-124">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6f1-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c6f1-125">See also</span></span>

- [<span data-ttu-id="7c6f1-126">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="7c6f1-126">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="7c6f1-127">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="7c6f1-127">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
