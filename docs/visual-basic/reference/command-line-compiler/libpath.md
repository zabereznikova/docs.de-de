---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 6285deb97b05659283071b8940fe8730890b98e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609862"
---
# <a name="-libpath"></a><span data-ttu-id="938fd-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="938fd-102">-libpath</span></span>
<span data-ttu-id="938fd-103">Gibt den Speicherort der Assemblys verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="938fd-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="938fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="938fd-104">Syntax</span></span>  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="938fd-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="938fd-105">Arguments</span></span>  
  
|<span data-ttu-id="938fd-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="938fd-106">Term</span></span>|<span data-ttu-id="938fd-107">Definition</span><span class="sxs-lookup"><span data-stu-id="938fd-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="938fd-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="938fd-108">Required.</span></span> <span data-ttu-id="938fd-109">Durch Semikolons getrennte Liste von Verzeichnissen, die der Compiler sucht, wenn eine referenzierte Assembly wurde nicht gefunden in entweder das aktuelle Arbeitsverzeichnis (das Verzeichnis, von dem Sie den Compiler aufrufen) oder die common Language Runtime-Systemverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="938fd-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="938fd-110">Wenn der Name des Verzeichnisses ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="938fd-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="938fd-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="938fd-111">Remarks</span></span>  
 <span data-ttu-id="938fd-112">Die `-libpath` Option gibt an, den Speicherort der Assemblys, die auf die verwiesen wird durch die [-Verweis](../../../visual-basic/reference/command-line-compiler/reference.md) Option.</span><span class="sxs-lookup"><span data-stu-id="938fd-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="938fd-113">Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:</span><span class="sxs-lookup"><span data-stu-id="938fd-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="938fd-114">Aktuelles Arbeitsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="938fd-114">Current working directory.</span></span> <span data-ttu-id="938fd-115">Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="938fd-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="938fd-116">Das Verzeichnis des CLR-Systems (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="938fd-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="938fd-117">Durch angegebenen Verzeichnisse `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="938fd-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="938fd-118">Von den LIB-Umgebungsvariablen angegebene Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="938fd-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="938fd-119">Die `-libpath` -Option ist additiv; Geben sie mehr als einmal an jeden vorherigen Wert angehängt.</span><span class="sxs-lookup"><span data-stu-id="938fd-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="938fd-120">Verwendung `-reference` um einen Assemblyverweis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="938fd-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="938fd-121">Zum Festlegen von/LIBPATH in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="938fd-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="938fd-122">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="938fd-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="938fd-123">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="938fd-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="938fd-124">2.  Klicken Sie auf die Registerkarte **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="938fd-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="938fd-125">3.  Klicken Sie auf die **Verweispfade...**  Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="938fd-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="938fd-126">4.  In der **Verweispfade** Dialogfeld Geben Sie den Namen des Verzeichnisses, in der **Ordner:** Feld.</span><span class="sxs-lookup"><span data-stu-id="938fd-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="938fd-127">5.  Klicken Sie auf **Ordner hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="938fd-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="938fd-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="938fd-128">Example</span></span>  
 <span data-ttu-id="938fd-129">Der folgende code kompiliert `T2.vb` eine .exe-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="938fd-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="938fd-130">Der Compiler sucht im Arbeitsverzeichnis, in das Stammverzeichnis von Laufwerk C: und im Verzeichnis von Laufwerk C: neuen Assemblys nach Assemblyverweisen.</span><span class="sxs-lookup"><span data-stu-id="938fd-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="938fd-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="938fd-131">See also</span></span>
- [<span data-ttu-id="938fd-132">Assemblys und der globale Assemblycache</span><span class="sxs-lookup"><span data-stu-id="938fd-132">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="938fd-133">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="938fd-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="938fd-134">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="938fd-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
