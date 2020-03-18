---
title: -lib (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
ms.openlocfilehash: 0c230147be055170ca015f27bd42bb096399405d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606817"
---
# <a name="-lib-c-compiler-options"></a><span data-ttu-id="35ff4-102">-lib (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="35ff4-102">-lib (C# Compiler Options)</span></span>
<span data-ttu-id="35ff4-103">Die Option **-lib** gibt den Speicherort der Assembly an, auf die verwiesen wird. Dies geschieht mithilfe der Option [-reference (C#-Compileroptionen)](./reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="35ff4-103">The **-lib** option specifies the location of assemblies referenced by means of the [-reference (C# Compiler Options)](./reference-compiler-option.md) option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35ff4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35ff4-104">Syntax</span></span>  
  
```console  
-lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="35ff4-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="35ff4-105">Arguments</span></span>  
 `dir1`  
 <span data-ttu-id="35ff4-106">Ein Verzeichnis, in dem der Compiler suchen kann, wenn die Assembly, auf die verwiesen wird, im aktuellen Arbeitsverzeichnis nicht gefunden werden kann (dort wo der Compiler aufgerufen wird) oder im Verzeichnis des CLR-Systems.</span><span class="sxs-lookup"><span data-stu-id="35ff4-106">A directory for the compiler to look in if a referenced assembly is not found in the current working directory (the directory from which you are invoking the compiler) or in the common language runtime's system directory.</span></span>  
  
 `dir2`  
 <span data-ttu-id="35ff4-107">Mindestens ein zusätzliches Verzeichnis, in dem nach Assemblyverweisen gesucht werden kann.</span><span class="sxs-lookup"><span data-stu-id="35ff4-107">One or more additional directories to search in for assembly references.</span></span> <span data-ttu-id="35ff4-108">Trennen Sie zusätzliche Verzeichnisnamen mit einem Komma, aber ohne Leerzeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="35ff4-108">Separate additional directory names with a comma, and without white space between them.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35ff4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35ff4-109">Remarks</span></span>  
 <span data-ttu-id="35ff4-110">Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:</span><span class="sxs-lookup"><span data-stu-id="35ff4-110">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="35ff4-111">Aktuelles Arbeitsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="35ff4-111">Current working directory.</span></span> <span data-ttu-id="35ff4-112">Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="35ff4-112">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="35ff4-113">Das Verzeichnis des CLR-Systems (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="35ff4-113">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="35ff4-114">Von **-lib** angegebene Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="35ff4-114">Directories specified by **-lib**.</span></span>  
  
4. <span data-ttu-id="35ff4-115">Von den LIB-Umgebungsvariablen angegebene Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="35ff4-115">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="35ff4-116">Verwenden Sie **-reference**, um einen Assemblyverweis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="35ff4-116">Use **-reference** to specify an assembly reference.</span></span>  
  
 <span data-ttu-id="35ff4-117">**-lib** ist additiv. Wenn es mehr als einmal angegeben wird, wird es an jeden vorherigen Wert angehängt.</span><span class="sxs-lookup"><span data-stu-id="35ff4-117">**-lib** is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="35ff4-118">Alternativ zu **-lib** können Sie auch alle erforderlichen Assemblys direkt in das Arbeitsverzeichnis kopieren. Dadurch können Sie den Namen der Assembly ganz einfach an **-reference** übergeben.</span><span class="sxs-lookup"><span data-stu-id="35ff4-118">An alternative to using **-lib** is to copy into the working directory any required assemblies; this will allow you to simply pass the assembly name to **-reference**.</span></span> <span data-ttu-id="35ff4-119">Anschließend können Sie die Assemblys wieder aus dem Arbeitsverzeichnis löschen.</span><span class="sxs-lookup"><span data-stu-id="35ff4-119">You can then delete the assemblies from the working directory.</span></span> <span data-ttu-id="35ff4-120">Da der Pfad der abhängigen Assembly nicht im Assemblymanifest angegeben ist, kann die Anwendung auf dem Zielcomputer gestartet werden. Sie findet und verwendet die Assembly dann im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="35ff4-120">Since the path to the dependent assembly is not specified in the assembly manifest, the application can be started on the target computer and will find and use the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="35ff4-121">Nur weil der Compiler auf die Assembly verweisen kann, heißt das nicht, dass die CLR die Assembly zur Laufzeit finden und laden kann.</span><span class="sxs-lookup"><span data-stu-id="35ff4-121">Because the compiler can reference the assembly does not imply the common language runtime will be able to find and load the assembly at runtime.</span></span> <span data-ttu-id="35ff4-122">Weitere Informationen dazu, wie die Laufzeit nach verwiesenen Assemblys sucht, finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="35ff4-122">See [How the Runtime Locates Assemblies](../../../framework/deployment/how-the-runtime-locates-assemblies.md) for details on how the runtime searches for referenced assemblies.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="35ff4-123">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="35ff4-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="35ff4-124">Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="35ff4-124">Open the project's **Property Pages** dialog box.</span></span>  
  
2. <span data-ttu-id="35ff4-125">Klicken Sie auf die Eigenschaftenseite **Verweispfad**.</span><span class="sxs-lookup"><span data-stu-id="35ff4-125">Click the **References Path** property page.</span></span>  
  
3. <span data-ttu-id="35ff4-126">Modifizieren Sie den Inhalt des Listenfelds.</span><span class="sxs-lookup"><span data-stu-id="35ff4-126">Modify the contents of the list box.</span></span>  
  
 <span data-ttu-id="35ff4-127">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span><span class="sxs-lookup"><span data-stu-id="35ff4-127">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35ff4-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35ff4-128">Example</span></span>  
 <span data-ttu-id="35ff4-129">Kompilieren Sie „t2.cs“, um eine EXE-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35ff4-129">Compile t2.cs to create an .exe file.</span></span> <span data-ttu-id="35ff4-130">Der Compiler sucht im Arbeitsverzeichnis und im Stammverzeichnis des Laufwerks C nach Assemblyverweisen.</span><span class="sxs-lookup"><span data-stu-id="35ff4-130">The compiler will look in the working directory and in the root directory of the C drive for assembly references.</span></span>  
  
```console  
csc -lib:c:\ -reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="35ff4-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35ff4-131">See also</span></span>

- [<span data-ttu-id="35ff4-132">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="35ff4-132">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="35ff4-133">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="35ff4-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
