---
title: / Reference (Visual Basic) | Microsoft-Dokumentation
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
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
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
ms.openlocfilehash: 6870c0b6008124bad18f8eba9207d06e085f2307
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="reference-visual-basic"></a><span data-ttu-id="a77fa-102">/reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a77fa-102">/reference (Visual Basic)</span></span>
<span data-ttu-id="a77fa-103">Veranlasst den Compiler, Typinformationen in den angegebenen Assemblys für das Projekt verfügbar, das Sie gerade kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a77fa-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a77fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a77fa-104">Syntax</span></span>  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="a77fa-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="a77fa-105">Arguments</span></span>  
  
|<span data-ttu-id="a77fa-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="a77fa-106">Term</span></span>|<span data-ttu-id="a77fa-107">Definition</span><span class="sxs-lookup"><span data-stu-id="a77fa-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="a77fa-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a77fa-108">Required.</span></span> <span data-ttu-id="a77fa-109">Durch Trennzeichen getrennte Liste von Assemblydateinamen.</span><span class="sxs-lookup"><span data-stu-id="a77fa-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="a77fa-110">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="a77fa-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a77fa-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a77fa-111">Remarks</span></span>  
 <span data-ttu-id="a77fa-112">Die importierten Dateien müssen Assemblymetadaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="a77fa-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="a77fa-113">Es werden nur öffentliche Typen außerhalb der Assembly sichtbar.</span><span class="sxs-lookup"><span data-stu-id="a77fa-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="a77fa-114">Die [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) -Option importiert Metadaten aus einem Modul.</span><span class="sxs-lookup"><span data-stu-id="a77fa-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="a77fa-115">Wenn Sie eine Assembly (Assembly A) verweisen, die wiederum verweist auf eine andere Assembly (Assembly B), müssen Sie auf Assembly B verweisen wenn:</span><span class="sxs-lookup"><span data-stu-id="a77fa-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="a77fa-116">Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.</span><span class="sxs-lookup"><span data-stu-id="a77fa-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="a77fa-117">Ein Feld, Eigenschaft, Ereignis oder -Methode, die einen Rückgabetyp für oder Parametertyp aus Assembly B wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a77fa-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="a77fa-118">Verwendung [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) an das Verzeichnis, in dem eine oder mehrere der Assemblyverweise befindet.</span><span class="sxs-lookup"><span data-stu-id="a77fa-118">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="a77fa-119">Der Compiler einen Typ in einer Assembly (nicht in einem Modul) erkennt muss er gezwungen werden, den Typ aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="a77fa-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="a77fa-120">Ein Beispiel dafür, wie Sie dies tun können, ist eine Instanz des Typs zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a77fa-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="a77fa-121">Andere Methoden sind auflösen Typnamen in einer Assembly für den Compiler verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a77fa-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="a77fa-122">Wenn Sie von einem Typ in einer Assembly erben, wird der Name z. B. dann an den Compiler bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a77fa-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="a77fa-123">Der Vbc.rsp-Antwortdatei, die häufig Verweise verwendet [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys wird standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="a77fa-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="a77fa-124">Verwenden Sie `/noconfig` , wenn Sie nicht, dass den Compiler Vbc.rsp verwendet möchten.</span><span class="sxs-lookup"><span data-stu-id="a77fa-124">Use `/noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="a77fa-125">Die Kurzform der `/reference` ist `/r`.</span><span class="sxs-lookup"><span data-stu-id="a77fa-125">The short form of `/reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a77fa-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a77fa-126">Example</span></span>  
 <span data-ttu-id="a77fa-127">Der folgende Code kompiliert Quelldatei I`nput.vb` und verweisen auf Assemblys von M`etad1.dll` und M`etad2.dll` zu O`ut.exe`.</span><span class="sxs-lookup"><span data-stu-id="a77fa-127">The following code compiles source file I`nput.vb` and reference assemblies from M`etad1.dll` and M`etad2.dll` to produce O`ut.exe`.</span></span>  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a77fa-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a77fa-128">See Also</span></span>  
 <span data-ttu-id="a77fa-129">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="a77fa-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="a77fa-130"> [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="a77fa-130"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="a77fa-131"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="a77fa-131"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="a77fa-132"> [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md) </span><span class="sxs-lookup"><span data-stu-id="a77fa-132"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span></span>  
<span data-ttu-id="a77fa-133"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="a77fa-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
