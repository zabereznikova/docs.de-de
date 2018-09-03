---
title: -keycontainer (C#-Compileroptionen)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: 57d3acb4fe128e07020bfe7c85ed86563b16f40a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467544"
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="05b2a-102">-keycontainer (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="05b2a-102">-keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="05b2a-103">Gibt den Namen des kryptografischen Schlüsselcontainers an.</span><span class="sxs-lookup"><span data-stu-id="05b2a-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05b2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05b2a-104">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="05b2a-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="05b2a-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="05b2a-106">Der Name des Containers mit dem Schlüssel für einen starken Namen</span><span class="sxs-lookup"><span data-stu-id="05b2a-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05b2a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05b2a-107">Remarks</span></span>  
 <span data-ttu-id="05b2a-108">Wenn die Option **-keycontainer** verwendet wird, erstellt der Compiler eine teilbare Komponente.</span><span class="sxs-lookup"><span data-stu-id="05b2a-108">When the **-keycontainer** option is used, the compiler creates a sharable component.</span></span> <span data-ttu-id="05b2a-109">Der Compiler fügt einen öffentlichen Schlüssel vom angegebenen Container in das Assemblymanifest ein und signiert die endgültige Assembly mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="05b2a-109">The compiler inserts a public key from the specified container into the assembly manifest and signs the final assembly with the private key.</span></span> <span data-ttu-id="05b2a-110">Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="05b2a-110">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="05b2a-111">`sn -i` installiert das Schlüsselpaar im Container.</span><span class="sxs-lookup"><span data-stu-id="05b2a-111">`sn -i` installs the key pair into a container.</span></span> <span data-ttu-id="05b2a-112">Diese Option wird nicht unterstützt, wenn der Compiler auf CoreCLR ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="05b2a-112">This option is not supported when the compiler runs on CoreCLR.</span></span> <span data-ttu-id="05b2a-113">Verwenden Sie zum Signieren einer Assembly beim Erstellen auf CoreCLR die Option [-keyfile](keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="05b2a-113">To sign an assembly when building on CoreCLR, use the [-keyfile](keyfile-compiler-option.md) option.</span></span>
  
 <span data-ttu-id="05b2a-114">Wenn Sie mit der Option [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, wenn Sie dieses Modul in eine Assembly mit [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="05b2a-114">If you compile with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="05b2a-115">Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.</span><span class="sxs-lookup"><span data-stu-id="05b2a-115">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="05b2a-116">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="05b2a-116">You can also pass your encryption information to the compiler with [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span></span> <span data-ttu-id="05b2a-117">Verwenden Sie [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md), wenn Sie den in das Assemblymanifest eingefügten Schlüssel verwenden, aber das Signieren der Assembly bis nach deren verzögern möchten, bis diese getestet wurde.</span><span class="sxs-lookup"><span data-stu-id="05b2a-117">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="05b2a-118">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) und [Verzögertes Signieren einer Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="05b2a-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="05b2a-119">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="05b2a-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="05b2a-120">Diese Compileroption ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05b2a-120">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="05b2a-121">Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> programmgesteuert auf diese Compileroption zugreifen.</span><span class="sxs-lookup"><span data-stu-id="05b2a-121">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b2a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05b2a-122">See Also</span></span>

- [<span data-ttu-id="05b2a-123">C#-Compileroption „-keyfile“</span><span class="sxs-lookup"><span data-stu-id="05b2a-123">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="05b2a-124">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="05b2a-124">C# Compiler Options</span></span>](index.md)  
- [<span data-ttu-id="05b2a-125">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="05b2a-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
