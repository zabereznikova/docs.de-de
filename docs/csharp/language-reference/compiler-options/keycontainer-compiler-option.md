---
title: -keycontainer (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0292ff38b1d03f5960a20858fbb9c42a6aff1f43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="keycontainer-c-compiler-options"></a><span data-ttu-id="43e92-102">/keycontainer (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="43e92-102">/keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="43e92-103">Gibt den Namen des kryptografischen Schlüsselcontainers an.</span><span class="sxs-lookup"><span data-stu-id="43e92-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43e92-104">Syntax</span></span>  
  
```console  
/keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="43e92-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="43e92-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="43e92-106">Der Name des Containers mit dem Schlüssel für einen starken Namen</span><span class="sxs-lookup"><span data-stu-id="43e92-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43e92-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43e92-107">Remarks</span></span>  
 <span data-ttu-id="43e92-108">Wenn die Option **/keycontainer** verwendet wird, erstellt der Compiler eine teilbare Komponente, indem er einen öffentlichen Schlüssel aus dem angegebenen Container in das Assemblymanifest einfügt und die endgültige Assembly mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="43e92-108">When the **/keycontainer** option is used, the compiler creates a sharable component by inserting a public key from the specified container into the assembly manifest and signing the final assembly with the private key.</span></span> <span data-ttu-id="43e92-109">Geben Sie sn -k `file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="43e92-109">To generate a key file, type sn -k `file` at the command line.</span></span> <span data-ttu-id="43e92-110">„sn -i“ installiert das Schlüsselpaar im Container.</span><span class="sxs-lookup"><span data-stu-id="43e92-110">sn -i installs the key pair into a container.</span></span>  
  
 <span data-ttu-id="43e92-111">Wenn Sie mit der Option [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, wenn Sie dieses Modul in eine Assembly mit [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="43e92-111">If you compile with [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="43e92-112">Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.</span><span class="sxs-lookup"><span data-stu-id="43e92-112">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="43e92-113">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="43e92-113">You can also pass your encryption information to the compiler with [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span></span> <span data-ttu-id="43e92-114">Verwenden Sie [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md), wenn Sie den in das Assemblymanifest eingefügten Schlüssel verwenden, aber das Signieren der Assembly bis nach deren Prüfung verzögern möchten.</span><span class="sxs-lookup"><span data-stu-id="43e92-114">Use [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="43e92-115">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) und [Verzögertes Signieren einer Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="43e92-115">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="43e92-116">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="43e92-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="43e92-117">Diese Compileroption ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43e92-117">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="43e92-118">Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> programmgesteuert auf diese Compileroption zugreifen.</span><span class="sxs-lookup"><span data-stu-id="43e92-118">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e92-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43e92-119">See Also</span></span>  
 [<span data-ttu-id="43e92-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="43e92-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="43e92-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="43e92-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
