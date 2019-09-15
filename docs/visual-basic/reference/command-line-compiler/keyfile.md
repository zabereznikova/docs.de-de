---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 30b890cf3d523d1e33b433a1ff6109759bd9a5e3
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972327"
---
# <a name="-keyfile"></a><span data-ttu-id="fdd64-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="fdd64-102">-keyfile</span></span>
<span data-ttu-id="fdd64-103">Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="fdd64-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdd64-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdd64-104">Syntax</span></span>  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="fdd64-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="fdd64-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="fdd64-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fdd64-106">Required.</span></span> <span data-ttu-id="fdd64-107">Die Datei, die den Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="fdd64-107">File that contains the key.</span></span> <span data-ttu-id="fdd64-108">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.</span><span class="sxs-lookup"><span data-stu-id="fdd64-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdd64-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdd64-109">Remarks</span></span>  
 <span data-ttu-id="fdd64-110">Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="fdd64-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="fdd64-111">Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="fdd64-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="fdd64-112">Weitere Informationen finden Sie unter [Sn. exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="fdd64-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="fdd64-113">Wenn Sie mit `-target:module`kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly integriert, die beim Kompilieren einer Assembly mit [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fdd64-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="fdd64-114">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="fdd64-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="fdd64-115">Verwenden Sie [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fdd64-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="fdd64-116">Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyFileAttribute>) im Quellcode für ein beliebiges Microsoft Intermediate Language-Modul angeben.</span><span class="sxs-lookup"><span data-stu-id="fdd64-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="fdd64-117">Für den Fall `-keyfile` , dass sowohl als auch [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) (entweder über eine Befehlszeilenoption oder ein benutzerdefiniertes Attribut) in derselben Kompilierung angegeben ist, versucht der Compiler zunächst, den Schlüssel Container zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fdd64-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="fdd64-118">Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert.</span><span class="sxs-lookup"><span data-stu-id="fdd64-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="fdd64-119">Wenn der Compiler den Schlüssel Container nicht findet, wird versucht, die mit angegebene Datei `-keyfile`zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="fdd64-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="fdd64-120">Wenn dies erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüssel Container installiert (ähnlich wie `sn -i`), sodass der Schlüssel Container bei der nächsten Kompilierung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="fdd64-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="fdd64-121">Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="fdd64-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="fdd64-122">Weitere Informationen zum Signieren einer Assembly finden [Sie unter Erstellen und verwenden](../../../standard/assembly/create-use-strong-named.md) von Assemblys mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="fdd64-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdd64-123">Die `-keyfile` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="fdd64-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdd64-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdd64-124">Example</span></span>  
 <span data-ttu-id="fdd64-125">Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.</span><span class="sxs-lookup"><span data-stu-id="fdd64-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdd64-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdd64-126">See also</span></span>

- [<span data-ttu-id="fdd64-127">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="fdd64-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="fdd64-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="fdd64-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fdd64-129">-Verweis (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdd64-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="fdd64-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="fdd64-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
