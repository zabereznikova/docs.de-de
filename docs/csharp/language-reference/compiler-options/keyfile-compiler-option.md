---
description: -keyfile (C#-Compileroptionen)
title: -keyfile (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: a97fc00201be1cf8043fc353b20ef447468a06bf
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125487"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="ae8c1-103">-keyfile (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ae8c1-103">-keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="ae8c1-104">Gibt den Dateinamen mit dem kryptografischen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-104">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae8c1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae8c1-105">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae8c1-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="ae8c1-106">Arguments</span></span>  
  
|<span data-ttu-id="ae8c1-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="ae8c1-107">Term</span></span>|<span data-ttu-id="ae8c1-108">Definition</span><span class="sxs-lookup"><span data-stu-id="ae8c1-108">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="ae8c1-109">Der Name der Datei mit dem Schlüssel mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-109">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae8c1-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ae8c1-110">Remarks</span></span>  
 <span data-ttu-id="ae8c1-111">Wenn diese Option verwendet wird, fügt der Compiler den öffentlichen Schlüssel von der angegebenen Datei in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-111">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="ae8c1-112">Geben Sie sn -k `file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-112">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="ae8c1-113">Wenn Sie mit der Option **-target:module** kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, die erstellt wird, wenn Sie eine Assembly mit [-addmodule](./addmodule-compiler-option.md) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-113">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="ae8c1-114">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keycontainer](./keycontainer-compiler-option.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-114">You can also pass your encryption information to the compiler with [-keycontainer](./keycontainer-compiler-option.md).</span></span> <span data-ttu-id="ae8c1-115">Verwenden Sie [-delaysign](./delaysign-compiler-option.md), wenn die Assembly teilweise signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-115">Use [-delaysign](./delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="ae8c1-116">Wenn für die gleiche Kompilierung sowohl „-keyfile“ als auch „-keycontainer“ angegeben werden (über eine Befehlszeilenoption oder ein benutzerdefiniertes Attribut), versucht der Compiler zunächst, den Schlüsselcontainer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-116">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="ae8c1-117">Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-117">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="ae8c1-118">Wenn den Compiler den Schlüsselcontainer nicht findet, wird versucht, die mit „-keyfile“ angegebene Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-118">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="ae8c1-119">Wenn dies erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüsselcontainer installiert (vergleichbar mit „sn -i“), sodass der Schlüsselcontainer bei der nächsten Kompilierung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-119">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="ae8c1-120">Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-120">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="ae8c1-121">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md) und [Verzögertes Signieren einer Assembly](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="ae8c1-121">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ae8c1-122">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="ae8c1-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ae8c1-123">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-123">Open the **Properties** page for the project.</span></span>  
  
2. <span data-ttu-id="ae8c1-124">Klicken Sie auf die Eigenschaftenseite **Signieren**.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-124">Click the **Signing** property page.</span></span>  
  
3. <span data-ttu-id="ae8c1-125">Modifizieren Sie die Eigenschaft **Schlüsseldatei mit starkem Namen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-125">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="ae8c1-126">Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A> programmgesteuert auf diese Compileroption zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ae8c1-126">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8c1-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae8c1-127">See also</span></span>

- [<span data-ttu-id="ae8c1-128">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="ae8c1-128">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ae8c1-129">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="ae8c1-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
