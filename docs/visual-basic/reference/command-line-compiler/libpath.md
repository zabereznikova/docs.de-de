---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 9a5822a097828f818da020735c3822e86eb3236b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716635"
---
# <a name="-libpath"></a><span data-ttu-id="77126-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="77126-102">-libpath</span></span>
<span data-ttu-id="77126-103">Gibt den Speicherort der Verweisassemblys an.</span><span class="sxs-lookup"><span data-stu-id="77126-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77126-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77126-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="77126-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="77126-105">Arguments</span></span>  
  
|<span data-ttu-id="77126-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="77126-106">Term</span></span>|<span data-ttu-id="77126-107">Definition</span><span class="sxs-lookup"><span data-stu-id="77126-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="77126-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77126-108">Required.</span></span> <span data-ttu-id="77126-109">Eine durch Semikolons getrennte Liste von Verzeichnissen, in denen der Compiler suchen kann, wenn die Assembly, auf die verwiesen wird, im aktuellen Arbeitsverzeichnis (das Verzeichnis, in dem Sie den Compiler aufrufen) oder im CLR-Systemverzeichnis (Common Language Runtime) nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="77126-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="77126-110">Wenn der Verzeichnisname ein Leerzeichen enthält, müssen Sie den Name in Anführungszeichen (" ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="77126-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77126-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77126-111">Remarks</span></span>  
 <span data-ttu-id="77126-112">Die `-libpath`-Option gibt den Speicherort der Assemblys an, auf die durch die [-reference](../../../visual-basic/reference/command-line-compiler/reference.md)-Option verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="77126-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="77126-113">Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:</span><span class="sxs-lookup"><span data-stu-id="77126-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="77126-114">Aktuelles Arbeitsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="77126-114">Current working directory.</span></span> <span data-ttu-id="77126-115">Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="77126-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="77126-116">Das Verzeichnis des CLR-Systems (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="77126-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="77126-117">Von `-libpath` angegebene Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="77126-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="77126-118">Von den LIB-Umgebungsvariablen angegebene Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="77126-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="77126-119">Die `-libpath`-Option ist additiv. Wenn sie mehr als einmal angegeben wird, wird sie an jeden vorherigen Wert angehängt.</span><span class="sxs-lookup"><span data-stu-id="77126-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="77126-120">Verwenden Sie `-reference`, um einen Assemblyverweis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="77126-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="77126-121">So legen Sie -libpath in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="77126-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="77126-122">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="77126-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="77126-123">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="77126-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="77126-124">2.  Klicken Sie auf die Registerkarte **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="77126-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="77126-125">3.  Klicken Sie auf die Schaltfläche **Verweispfade…** .</span><span class="sxs-lookup"><span data-stu-id="77126-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="77126-126">4.  Geben Sie im Dialogfeld **Verweispfade** den Verzeichnisname im Feld **Ordner:** ein.</span><span class="sxs-lookup"><span data-stu-id="77126-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="77126-127">5.  Klicken Sie auf **Ordner hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="77126-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="77126-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77126-128">Example</span></span>  
 <span data-ttu-id="77126-129">Der folgende Code kompiliert `T2.vb`, um eine EXE-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="77126-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="77126-130">Der Compiler sucht im Arbeitsverzeichnis, im Stammverzeichnis des Laufwerks C: und im Verzeichnis „Neue Verzeichnisse“ des Laufwerks C: nach Assemblyverweisen.</span><span class="sxs-lookup"><span data-stu-id="77126-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="77126-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77126-131">See also</span></span>

- [<span data-ttu-id="77126-132">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="77126-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="77126-133">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="77126-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="77126-134">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="77126-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
