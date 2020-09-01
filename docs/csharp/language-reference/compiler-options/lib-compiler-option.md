---
description: -lib (C#-Compileroptionen)
title: -lib (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
ms.openlocfilehash: e53c54dc446d9fea87a9b7a336a38ffaa31704e9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125448"
---
# <a name="-lib-c-compiler-options"></a><span data-ttu-id="04793-103">-lib (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="04793-103">-lib (C# Compiler Options)</span></span>
<span data-ttu-id="04793-104">Die Option **-lib** gibt den Speicherort der Assembly an, auf die verwiesen wird. Dies geschieht mithilfe der Option [-reference (C#-Compileroptionen)](./reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="04793-104">The **-lib** option specifies the location of assemblies referenced by means of the [-reference (C# Compiler Options)](./reference-compiler-option.md) option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04793-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="04793-105">Syntax</span></span>  
  
```console  
-lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="04793-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="04793-106">Arguments</span></span>  
 `dir1`  
 <span data-ttu-id="04793-107">Ein Verzeichnis, in dem der Compiler suchen kann, wenn die Assembly, auf die verwiesen wird, im aktuellen Arbeitsverzeichnis nicht gefunden werden kann (dort wo der Compiler aufgerufen wird) oder im Verzeichnis des CLR-Systems.</span><span class="sxs-lookup"><span data-stu-id="04793-107">A directory for the compiler to look in if a referenced assembly is not found in the current working directory (the directory from which you are invoking the compiler) or in the common language runtime's system directory.</span></span>  
  
 `dir2`  
 <span data-ttu-id="04793-108">Mindestens ein zusätzliches Verzeichnis, in dem nach Assemblyverweisen gesucht werden kann.</span><span class="sxs-lookup"><span data-stu-id="04793-108">One or more additional directories to search in for assembly references.</span></span> <span data-ttu-id="04793-109">Trennen Sie zusätzliche Verzeichnisnamen mit einem Komma, aber ohne Leerzeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="04793-109">Separate additional directory names with a comma, and without white space between them.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04793-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="04793-110">Remarks</span></span>  
 <span data-ttu-id="04793-111">Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:</span><span class="sxs-lookup"><span data-stu-id="04793-111">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="04793-112">Aktuelles Arbeitsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="04793-112">Current working directory.</span></span> <span data-ttu-id="04793-113">Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="04793-113">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="04793-114">Das Verzeichnis des CLR-Systems (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="04793-114">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="04793-115">Von **-lib** angegebene Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="04793-115">Directories specified by **-lib**.</span></span>  
  
4. <span data-ttu-id="04793-116">Von den LIB-Umgebungsvariablen angegebene Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="04793-116">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="04793-117">Verwenden Sie **-reference**, um einen Assemblyverweis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="04793-117">Use **-reference** to specify an assembly reference.</span></span>  
  
 <span data-ttu-id="04793-118">**-lib** ist additiv. Wenn es mehr als einmal angegeben wird, wird es an jeden vorherigen Wert angehängt.</span><span class="sxs-lookup"><span data-stu-id="04793-118">**-lib** is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="04793-119">Alternativ zu **-lib** können Sie auch alle erforderlichen Assemblys direkt in das Arbeitsverzeichnis kopieren. Dadurch können Sie den Namen der Assembly ganz einfach an **-reference** übergeben.</span><span class="sxs-lookup"><span data-stu-id="04793-119">An alternative to using **-lib** is to copy into the working directory any required assemblies; this will allow you to simply pass the assembly name to **-reference**.</span></span> <span data-ttu-id="04793-120">Anschließend können Sie die Assemblys wieder aus dem Arbeitsverzeichnis löschen.</span><span class="sxs-lookup"><span data-stu-id="04793-120">You can then delete the assemblies from the working directory.</span></span> <span data-ttu-id="04793-121">Da der Pfad der abhängigen Assembly nicht im Assemblymanifest angegeben ist, kann die Anwendung auf dem Zielcomputer gestartet werden. Sie findet und verwendet die Assembly dann im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="04793-121">Since the path to the dependent assembly is not specified in the assembly manifest, the application can be started on the target computer and will find and use the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="04793-122">Nur weil der Compiler auf die Assembly verweisen kann, heißt das nicht, dass die CLR die Assembly zur Laufzeit finden und laden kann.</span><span class="sxs-lookup"><span data-stu-id="04793-122">Because the compiler can reference the assembly does not imply the common language runtime will be able to find and load the assembly at runtime.</span></span> <span data-ttu-id="04793-123">Weitere Informationen dazu, wie die Laufzeit nach verwiesenen Assemblys sucht, finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="04793-123">See [How the Runtime Locates Assemblies](../../../framework/deployment/how-the-runtime-locates-assemblies.md) for details on how the runtime searches for referenced assemblies.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="04793-124">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="04793-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="04793-125">Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="04793-125">Open the project's **Property Pages** dialog box.</span></span>  
  
2. <span data-ttu-id="04793-126">Klicken Sie auf die Eigenschaftenseite **Verweispfad**.</span><span class="sxs-lookup"><span data-stu-id="04793-126">Click the **References Path** property page.</span></span>  
  
3. <span data-ttu-id="04793-127">Modifizieren Sie den Inhalt des Listenfelds.</span><span class="sxs-lookup"><span data-stu-id="04793-127">Modify the contents of the list box.</span></span>  
  
 <span data-ttu-id="04793-128">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span><span class="sxs-lookup"><span data-stu-id="04793-128">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04793-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04793-129">Example</span></span>  
 <span data-ttu-id="04793-130">Kompilieren Sie „t2.cs“, um eine EXE-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="04793-130">Compile t2.cs to create an .exe file.</span></span> <span data-ttu-id="04793-131">Der Compiler sucht im Arbeitsverzeichnis und im Stammverzeichnis des Laufwerks C nach Assemblyverweisen.</span><span class="sxs-lookup"><span data-stu-id="04793-131">The compiler will look in the working directory and in the root directory of the C drive for assembly references.</span></span>  
  
```console  
csc -lib:c:\ -reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="04793-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04793-132">See also</span></span>

- [<span data-ttu-id="04793-133">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="04793-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="04793-134">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="04793-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
