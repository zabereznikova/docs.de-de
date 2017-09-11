---
title: / keyfile | Microsoft-Dokumentation
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
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
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
ms.openlocfilehash: ec63fd990b8524bbc212a33714ec8380a8c99f32
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="keyfile"></a><span data-ttu-id="9a639-102">/keyfile</span><span class="sxs-lookup"><span data-stu-id="9a639-102">/keyfile</span></span>
<span data-ttu-id="9a639-103">Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9a639-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a639-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a639-104">Syntax</span></span>  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="9a639-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9a639-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="9a639-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9a639-106">Required.</span></span> <span data-ttu-id="9a639-107">Datei, die den Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="9a639-107">File that contains the key.</span></span> <span data-ttu-id="9a639-108">Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="9a639-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a639-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a639-109">Remarks</span></span>  
 <span data-ttu-id="9a639-110">Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="9a639-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="9a639-111">Um eine Schlüsseldatei zu generieren, geben Sie `sn -k file` in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="9a639-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="9a639-112">Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="9a639-112">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="9a639-113">Bei der Kompilierung mit `/target:module`, der Name der Schlüsseldatei im Modul gespeichert und in die Assembly, die erstellt wird, wenn eine Assembly mit aufgenommen [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="9a639-113">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="9a639-114">Sie können auch die Verschlüsselungsinformationen mit an den Compiler übergeben [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="9a639-114">You can also pass your encryption information to the compiler with [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="9a639-115">Verwendung [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) , wenn Sie eine Assembly teilweise signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a639-115">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="9a639-116">Sie können diese Option auch als benutzerdefiniertes Attribut angeben (<xref:System.Reflection.AssemblyKeyFileAttribute>) im Quellcode für ein beliebiges Microsoft intermediate Language-Modul.</xref:System.Reflection.AssemblyKeyFileAttribute></span><span class="sxs-lookup"><span data-stu-id="9a639-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="9a639-117">Sowohl `/keyfile` und [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) sind (entweder durch eine Befehlszeilenoption oder durch ein benutzerdefiniertes Attribut) in der gleichen Kompilierung angegeben, versucht der Compiler zuerst den Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="9a639-117">In case both `/keyfile` and [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="9a639-118">Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert.</span><span class="sxs-lookup"><span data-stu-id="9a639-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="9a639-119">Wenn der Compiler den Schlüsselcontainer nicht finden kann, versucht er mit angegebene Datei `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="9a639-119">If the compiler does not find the key container, it tries the file specified with `/keyfile`.</span></span> <span data-ttu-id="9a639-120">Wenn dies erfolgreich ist, die Assembly mit den Informationen in der Schlüsseldatei signiert wird und die Informationen im Schlüsselcontainer installiert ist (ähnlich wie `sn -i`), damit bei der nächsten Kompilierung die Schlüsselcontainer gültig sein soll.</span><span class="sxs-lookup"><span data-stu-id="9a639-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="9a639-121">Beachten Sie, dass eine Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="9a639-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="9a639-122">Finden Sie unter [erstellen und Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) für Weitere Informationen zum Signieren einer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="9a639-122">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a639-123">Die `/keyfile` Option ist nicht verfügbar der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Entwicklungsumgebung; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="9a639-123">The `/keyfile` option is not available from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a639-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a639-124">Example</span></span>  
 <span data-ttu-id="9a639-125">Im folgenden Code wird die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.</span><span class="sxs-lookup"><span data-stu-id="9a639-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a639-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a639-126">See Also</span></span>  
 <span data-ttu-id="9a639-127">[Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a639-127">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="9a639-128"> [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a639-128"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="9a639-129"> [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="9a639-129"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="9a639-130"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="9a639-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
