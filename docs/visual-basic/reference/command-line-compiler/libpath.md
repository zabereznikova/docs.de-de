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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716635"
---
# <a name="-libpath"></a><span data-ttu-id="74270-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="74270-102">-libpath</span></span>
<span data-ttu-id="74270-103">Gibt den Speicherort der referenzierten Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="74270-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74270-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74270-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="74270-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="74270-105">Arguments</span></span>  
  
|<span data-ttu-id="74270-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="74270-106">Term</span></span>|<span data-ttu-id="74270-107">Definition</span><span class="sxs-lookup"><span data-stu-id="74270-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="74270-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="74270-108">Required.</span></span> <span data-ttu-id="74270-109">Eine durch Semikolons getrennte Liste von Verzeichnissen, in denen der Compiler suchen soll, wenn eine referenzierte Assembly nicht im aktuellen Arbeitsverzeichnis (dem Verzeichnis, von dem Sie den Compiler aufrufen) oder im System Verzeichnis des Common Language Runtime gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="74270-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="74270-110">Wenn der Verzeichnisname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.</span><span class="sxs-lookup"><span data-stu-id="74270-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74270-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74270-111">Remarks</span></span>  
 <span data-ttu-id="74270-112">Die Option `-libpath` gibt den Speicherort der Assemblys an, auf die die Option [-Reference verweist](../../../visual-basic/reference/command-line-compiler/reference.md) .</span><span class="sxs-lookup"><span data-stu-id="74270-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="74270-113">Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:</span><span class="sxs-lookup"><span data-stu-id="74270-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="74270-114">Aktuelles Arbeitsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="74270-114">Current working directory.</span></span> <span data-ttu-id="74270-115">Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="74270-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="74270-116">Das Verzeichnis des CLR-Systems (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="74270-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="74270-117">Von `-libpath`angegebene Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="74270-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="74270-118">Von den LIB-Umgebungsvariablen angegebene Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="74270-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="74270-119">Die `-libpath` Option ist additiv. Wenn Sie den Wert mehrmals angeben, werden alle vorherigen Werte angehängt.</span><span class="sxs-lookup"><span data-stu-id="74270-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="74270-120">Verwenden Sie `-reference`, um einen Assemblyverweis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="74270-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="74270-121">So legen Sie "-LIBPATH" in der integrierten Entwicklungsumgebung von Visual Studio fest</span><span class="sxs-lookup"><span data-stu-id="74270-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="74270-122">1. Wählen Sie ein Projekt aus, das in **Projektmappen-Explorer**ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="74270-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="74270-123">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="74270-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="74270-124">2. Klicken Sie auf die Registerkarte **Verweise** .</span><span class="sxs-lookup"><span data-stu-id="74270-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="74270-125">3. Klicken Sie auf die Schaltfläche **Verweis Pfade...** .</span><span class="sxs-lookup"><span data-stu-id="74270-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="74270-126">4. Geben Sie im Dialogfeld **Verweis Pfade** den Verzeichnisnamen in das Feld **Ordner:** ein.</span><span class="sxs-lookup"><span data-stu-id="74270-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="74270-127">5. Klicken Sie auf **Ordner hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="74270-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="74270-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74270-128">Example</span></span>  
 <span data-ttu-id="74270-129">Mit dem folgenden Code wird `T2.vb` kompiliert, um eine exe-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74270-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="74270-130">Der Compiler sucht im Arbeitsverzeichnis im Stammverzeichnis des Laufwerks c: und im Verzeichnis neue Assemblys des Laufwerks c: nach Assemblyverweisen.</span><span class="sxs-lookup"><span data-stu-id="74270-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="74270-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74270-131">See also</span></span>

- [<span data-ttu-id="74270-132">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="74270-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="74270-133">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="74270-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="74270-134">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="74270-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
