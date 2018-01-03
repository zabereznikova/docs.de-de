---
title: /keyfile
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0be7d230f16750395aaceb3c94539546716b8fd
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="keyfile"></a><span data-ttu-id="7ab42-102">/keyfile</span><span class="sxs-lookup"><span data-stu-id="7ab42-102">/keyfile</span></span>
<span data-ttu-id="7ab42-103">Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="7ab42-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ab42-104">Syntax</span></span>  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="7ab42-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7ab42-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="7ab42-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ab42-106">Required.</span></span> <span data-ttu-id="7ab42-107">Datei, die den Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="7ab42-107">File that contains the key.</span></span> <span data-ttu-id="7ab42-108">Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="7ab42-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ab42-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ab42-109">Remarks</span></span>  
 <span data-ttu-id="7ab42-110">Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="7ab42-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="7ab42-111">Um eine Schlüsseldatei zu generieren, geben Sie `sn -k file` in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="7ab42-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="7ab42-112">Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)][Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="7ab42-112">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="7ab42-113">Beim Kompilieren mit `/target:module`, der Namen der Datei mit dem Schlüssel ist im Modul gespeichert und in die Assembly, die erstellt wird, wenn Sie eine Assembly mit Kompilieren integriert [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="7ab42-113">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="7ab42-114">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="7ab42-114">You can also pass your encryption information to the compiler with [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="7ab42-115">Verwenden Sie [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ab42-115">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="7ab42-116">Sie können diese Option auch als benutzerdefiniertes Attribut angeben (<xref:System.Reflection.AssemblyKeyFileAttribute>) im Quellcode für ein beliebiges Modul von Microsoft intermediate Language.</span><span class="sxs-lookup"><span data-stu-id="7ab42-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="7ab42-117">Sowohl `/keyfile` und [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) sind angegeben (entweder durch eine Befehlszeilenoption oder durch ein benutzerdefiniertes Attribut) in der gleichen Kompilierung, versucht der Compiler zunächst den Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="7ab42-117">In case both `/keyfile` and [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="7ab42-118">Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert.</span><span class="sxs-lookup"><span data-stu-id="7ab42-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="7ab42-119">Wenn der Compiler den Schlüsselcontainer nicht finden kann, versucht es mit angegebene Datei `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="7ab42-119">If the compiler does not find the key container, it tries the file specified with `/keyfile`.</span></span> <span data-ttu-id="7ab42-120">Wenn dies erfolgreich ist, die Assembly mit den Informationen in der Schlüsseldatei signiert wird und die Schlüsselinformationen im Schlüsselcontainer installiert wird (ähnlich wie `sn -i`), damit bei der nächsten Kompilierung die Schlüsselcontainer gültig sein soll.</span><span class="sxs-lookup"><span data-stu-id="7ab42-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="7ab42-121">Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="7ab42-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="7ab42-122">Finden Sie unter [erstellen und Verwenden von Assemblys](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="7ab42-122">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ab42-123">Die `/keyfile` Option ist nicht verfügbar in der [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Entwicklungsumgebung; ist verfügbar, nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7ab42-123">The `/keyfile` option is not available from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ab42-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ab42-124">Example</span></span>  
 <span data-ttu-id="7ab42-125">Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.</span><span class="sxs-lookup"><span data-stu-id="7ab42-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ab42-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ab42-126">See Also</span></span>  
 [<span data-ttu-id="7ab42-127">Assemblys und der globale Assemblycache</span><span class="sxs-lookup"><span data-stu-id="7ab42-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="7ab42-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="7ab42-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="7ab42-129">/ Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ab42-129">/reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="7ab42-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="7ab42-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
