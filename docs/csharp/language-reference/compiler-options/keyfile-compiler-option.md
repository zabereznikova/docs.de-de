---
title: -keyfile (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: bf271cc6b6887e930911071d4603b51daed55e61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970259"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="9b651-102">-keyfile (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="9b651-102">-keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="9b651-103">Gibt den Dateinamen mit dem kryptografischen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="9b651-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b651-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b651-104">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="9b651-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9b651-105">Arguments</span></span>  
  
|<span data-ttu-id="9b651-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="9b651-106">Term</span></span>|<span data-ttu-id="9b651-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9b651-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="9b651-108">Der Name der Datei mit dem Schlüssel mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="9b651-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b651-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b651-109">Remarks</span></span>  
 <span data-ttu-id="9b651-110">Wenn diese Option verwendet wird, fügt der Compiler den öffentlichen Schlüssel von der angegebenen Datei in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="9b651-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="9b651-111">Geben Sie sn -k `file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9b651-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="9b651-112">Wenn Sie mit der Option **-target:module** kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, die erstellt wird, wenn Sie eine Assembly mit [-addmodule](./addmodule-compiler-option.md) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="9b651-112">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="9b651-113">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keycontainer](./keycontainer-compiler-option.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="9b651-113">You can also pass your encryption information to the compiler with [-keycontainer](./keycontainer-compiler-option.md).</span></span> <span data-ttu-id="9b651-114">Verwenden Sie [-delaysign](./delaysign-compiler-option.md), wenn die Assembly teilweise signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b651-114">Use [-delaysign](./delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="9b651-115">Wenn für die gleiche Kompilierung sowohl „-keyfile“ als auch „-keycontainer“ angegeben werden (über eine Befehlszeilenoption oder ein benutzerdefiniertes Attribut), versucht der Compiler zunächst, den Schlüsselcontainer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b651-115">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="9b651-116">Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert.</span><span class="sxs-lookup"><span data-stu-id="9b651-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="9b651-117">Wenn den Compiler den Schlüsselcontainer nicht findet, wird versucht, die mit „-keyfile“ angegebene Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b651-117">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="9b651-118">Wenn dies erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüsselcontainer installiert (vergleichbar mit „sn -i“), sodass der Schlüsselcontainer bei der nächsten Kompilierung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="9b651-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="9b651-119">Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="9b651-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="9b651-120">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md) und [Verzögertes Signieren einer Assembly](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="9b651-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9b651-121">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="9b651-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="9b651-122">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="9b651-122">Open the **Properties** page for the project.</span></span>  
  
2. <span data-ttu-id="9b651-123">Klicken Sie auf die Eigenschaftenseite **Signieren**.</span><span class="sxs-lookup"><span data-stu-id="9b651-123">Click the **Signing** property page.</span></span>  
  
3. <span data-ttu-id="9b651-124">Modifizieren Sie die Eigenschaft **Schlüsseldatei mit starkem Namen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="9b651-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="9b651-125">Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A> programmgesteuert auf diese Compileroption zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9b651-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b651-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b651-126">See also</span></span>

- [<span data-ttu-id="9b651-127">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="9b651-127">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="9b651-128">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="9b651-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
