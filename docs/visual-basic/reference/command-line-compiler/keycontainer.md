---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 1666c7743f1116f86bc4457af53711cb6f1a6b7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579822"
---
# <a name="-keycontainer"></a><span data-ttu-id="816c6-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="816c6-102">-keycontainer</span></span>
<span data-ttu-id="816c6-103">Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="816c6-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="816c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="816c6-104">Syntax</span></span>  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="816c6-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="816c6-105">Arguments</span></span>  
  
|<span data-ttu-id="816c6-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="816c6-106">Term</span></span>|<span data-ttu-id="816c6-107">Definition</span><span class="sxs-lookup"><span data-stu-id="816c6-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="816c6-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="816c6-108">Required.</span></span> <span data-ttu-id="816c6-109">Containerdatei, die den Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="816c6-109">Container file that contains the key.</span></span> <span data-ttu-id="816c6-110">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn der Name ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="816c6-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="816c6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="816c6-111">Remarks</span></span>  
 <span data-ttu-id="816c6-112">Der Compiler erstellt die teilbare Komponente, indem er einen öffentlichen Schlüssel in das Assemblymanifest einfügt und die endgültige Assembly mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="816c6-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="816c6-113">Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="816c6-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="816c6-114">Die `-i` Option installiert das Schlüsselpaar in einem Container.</span><span class="sxs-lookup"><span data-stu-id="816c6-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="816c6-115">Weitere Informationen finden Sie unter [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="816c6-115">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="816c6-116">Bei der Kompilierung mit `-target:module`, der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly, die erstellt wird, wenn Sie eine Assembly mit integriert [- Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="816c6-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="816c6-117">Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.</span><span class="sxs-lookup"><span data-stu-id="816c6-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="816c6-118">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="816c6-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="816c6-119">Verwenden Sie [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="816c6-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="816c6-120">Finden Sie unter [erstellen und Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="816c6-120">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="816c6-121">Die `-keycontainer` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="816c6-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="816c6-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="816c6-122">Example</span></span>  
 <span data-ttu-id="816c6-123">Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt einen Schlüsselcontainer an.</span><span class="sxs-lookup"><span data-stu-id="816c6-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="816c6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="816c6-124">See also</span></span>
- [<span data-ttu-id="816c6-125">Assemblys und der globale Assemblycache</span><span class="sxs-lookup"><span data-stu-id="816c6-125">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="816c6-126">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="816c6-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="816c6-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="816c6-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="816c6-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="816c6-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
