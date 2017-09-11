---
title: / LIBPATH | Microsoft-Dokumentation
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
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: 16
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
ms.openlocfilehash: 7f24dd7707645f45677dcf7009e1adc64afaaa7c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="libpath"></a><span data-ttu-id="e067c-102">/libpath</span><span class="sxs-lookup"><span data-stu-id="e067c-102">/libpath</span></span>
<span data-ttu-id="e067c-103">Gibt den Speicherort der Assemblys verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e067c-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e067c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e067c-104">Syntax</span></span>  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="e067c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e067c-105">Arguments</span></span>  
  
|<span data-ttu-id="e067c-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e067c-106">Term</span></span>|<span data-ttu-id="e067c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e067c-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="e067c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e067c-108">Required.</span></span> <span data-ttu-id="e067c-109">Durch Semikolons getrennte Liste von Verzeichnissen, die der Compiler sucht, wenn eine Assembly nicht befindet sich entweder in das aktuelle Arbeitsverzeichnis (dem Verzeichnis, aus dem Sie den Compiler starten) oder die common Language Runtime-Systemverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e067c-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="e067c-110">Wenn der Verzeichnisname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="e067c-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e067c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e067c-111">Remarks</span></span>  
 <span data-ttu-id="e067c-112">Die `/libpath` Option gibt den Speicherort der Assemblys, auf die verwiesen wird die [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) Option.</span><span class="sxs-lookup"><span data-stu-id="e067c-112">The `/libpath` option specifies the location of assemblies referenced by the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="e067c-113">Der Compiler sucht nach Assemblyverweisen, die nicht voll in der folgenden Reihenfolge qualifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="e067c-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="e067c-114">Aktuelles Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e067c-114">Current working directory.</span></span> <span data-ttu-id="e067c-115">Dies ist das Verzeichnis, in dem der Compiler aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e067c-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="e067c-116">Die common Language Runtime-Systemverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e067c-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="e067c-117">Verzeichnisse, die durch angegebene `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="e067c-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="e067c-118">Durch die LIB-Umgebungsvariablen angegebenen Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="e067c-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="e067c-119">Die `/libpath` -Option ist additiv; Angabe es mehr als einmal an die vorherigen Werte angehängt.</span><span class="sxs-lookup"><span data-stu-id="e067c-119">The `/libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="e067c-120">Verwendung `/reference` um einen Assemblyverweis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e067c-120">Use `/reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="e067c-121">Zum Festlegen von/LIBPATH in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="e067c-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e067c-122">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e067c-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e067c-123">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e067c-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e067c-124">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="e067c-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="e067c-125">2.  Klicken Sie auf die **Verweise** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="e067c-125">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="e067c-126">3.  Klicken Sie auf die **Verweispfade... ** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="e067c-126">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="e067c-127">4.  In der **Verweispfade** Dialogfeld Geben Sie den Namen des Verzeichnisses, in dem **Ordner:** Feld.</span><span class="sxs-lookup"><span data-stu-id="e067c-127">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="e067c-128">5.  Klicken Sie auf **Ordner hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e067c-128">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e067c-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e067c-129">Example</span></span>  
 <span data-ttu-id="e067c-130">Der folgende code kompiliert `T2.vb` .exe-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e067c-130">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="e067c-131">Der Compiler sucht im Arbeitsverzeichnis, im Stammverzeichnis von Laufwerk C: und im Verzeichnis New Assemblies von Laufwerk C: für Assemblyverweise.</span><span class="sxs-lookup"><span data-stu-id="e067c-131">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e067c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e067c-132">See Also</span></span>  
 <span data-ttu-id="e067c-133">[Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="e067c-133">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="e067c-134"> [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="e067c-134"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="e067c-135"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="e067c-135"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
