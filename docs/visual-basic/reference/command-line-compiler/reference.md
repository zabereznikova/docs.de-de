---
title: -Referenz (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 203de45ed3a9e91adaf3237a827df6353f384bfb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182995"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="67273-102">-Referenz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67273-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="67273-103">Veranlasst den Compiler Typinformationen in den angegebenen Assemblys für das Projekt verfügbar sein, auf denen Sie aktuell kompilieren.</span><span class="sxs-lookup"><span data-stu-id="67273-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67273-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67273-104">Syntax</span></span>  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="67273-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="67273-105">Arguments</span></span>  
  
|<span data-ttu-id="67273-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="67273-106">Term</span></span>|<span data-ttu-id="67273-107">Definition</span><span class="sxs-lookup"><span data-stu-id="67273-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="67273-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="67273-108">Required.</span></span> <span data-ttu-id="67273-109">Durch Trennzeichen getrennte Liste von Assemblydateinamen.</span><span class="sxs-lookup"><span data-stu-id="67273-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="67273-110">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="67273-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67273-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67273-111">Remarks</span></span>  
 <span data-ttu-id="67273-112">Die Dateien, die Sie importieren, müssen Assemblymetadaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="67273-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="67273-113">Es sind nur öffentliche Typen außerhalb der Assembly sichtbar.</span><span class="sxs-lookup"><span data-stu-id="67273-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="67273-114">Die [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) Option importiert Metadaten aus einem Modul.</span><span class="sxs-lookup"><span data-stu-id="67273-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="67273-115">Wenn Sie eine Assembly (Assembly A) verweisen, die ihrerseits auf einer anderen Assembly (Assembly B) verweist, müssen Sie auf Assembly B verweisen wenn:</span><span class="sxs-lookup"><span data-stu-id="67273-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="67273-116">Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.</span><span class="sxs-lookup"><span data-stu-id="67273-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="67273-117">Es wird ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode aufgerufen, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.</span><span class="sxs-lookup"><span data-stu-id="67273-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="67273-118">Verwendung [- Libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) auf das Verzeichnis anzugeben, in denen eine oder mehrere der Assemblyverweise befinden.</span><span class="sxs-lookup"><span data-stu-id="67273-118">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="67273-119">Für den Compiler an, das Erkennen eines Typs in einer Assembly (nicht in einem Modul) muss er gezwungen werden, den Typ aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="67273-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="67273-120">Ein Beispiel dafür, wie Sie dies tun können, ist eine Instanz des Typs definieren.</span><span class="sxs-lookup"><span data-stu-id="67273-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="67273-121">Weitere Möglichkeiten sind verfügbar, Typnamen in einer Assembly für den Compiler aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="67273-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="67273-122">Wenn Sie von einem Typ in einer Assembly erben, wird z. B. der Typnamen klicken Sie dann an den Compiler bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="67273-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="67273-123">Der Vbc.rsp-Antwortdatei, die Verweise häufig verwendet [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys wird standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="67273-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="67273-124">Verwenden Sie `-noconfig` Wenn Sie nicht, dass den Compiler "vbc.rsp" zu verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="67273-124">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="67273-125">Die Kurzform von `-reference` ist `/r`.</span><span class="sxs-lookup"><span data-stu-id="67273-125">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67273-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67273-126">Example</span></span>  
 <span data-ttu-id="67273-127">Der folgende Befehl kompiliert die Quelldatei `Input.vb` und Verweisassemblys aus `Metad1.dll` und `Metad2.dll` erzeugt `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="67273-127">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="67273-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67273-128">See Also</span></span>  
 [<span data-ttu-id="67273-129">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="67273-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="67273-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="67273-130">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="67273-131">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67273-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="67273-132">Public</span><span class="sxs-lookup"><span data-stu-id="67273-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="67273-133">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="67273-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
