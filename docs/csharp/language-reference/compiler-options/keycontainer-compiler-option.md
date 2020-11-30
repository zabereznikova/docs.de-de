---
description: -keycontainer (C#-Compileroptionen)
title: -keycontainer (C#-Compileroptionen)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: 93ee5cd755a4fd6918d2a5825b63151a201a8f6a
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91152467"
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="6bccf-103">-keycontainer (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="6bccf-103">-keycontainer (C# Compiler Options)</span></span>

<span data-ttu-id="6bccf-104">Gibt den Namen des kryptografischen Schlüsselcontainers an.</span><span class="sxs-lookup"><span data-stu-id="6bccf-104">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bccf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bccf-105">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="6bccf-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="6bccf-106">Arguments</span></span>  

 `string`  
 <span data-ttu-id="6bccf-107">Der Name des Containers mit dem Schlüssel für einen starken Namen</span><span class="sxs-lookup"><span data-stu-id="6bccf-107">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bccf-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6bccf-108">Remarks</span></span>  

 <span data-ttu-id="6bccf-109">Wenn die Option **-keycontainer** verwendet wird, erstellt der Compiler eine teilbare Komponente.</span><span class="sxs-lookup"><span data-stu-id="6bccf-109">When the **-keycontainer** option is used, the compiler creates a sharable component.</span></span> <span data-ttu-id="6bccf-110">Der Compiler fügt einen öffentlichen Schlüssel vom angegebenen Container in das Assemblymanifest ein und signiert die endgültige Assembly mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6bccf-110">The compiler inserts a public key from the specified container into the assembly manifest and signs the final assembly with the private key.</span></span> <span data-ttu-id="6bccf-111">Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6bccf-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="6bccf-112">`sn -i` installiert das Schlüsselpaar im Container.</span><span class="sxs-lookup"><span data-stu-id="6bccf-112">`sn -i` installs the key pair into a container.</span></span> <span data-ttu-id="6bccf-113">Diese Option wird nicht unterstützt, wenn der Compiler auf CoreCLR ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6bccf-113">This option is not supported when the compiler runs on CoreCLR.</span></span> <span data-ttu-id="6bccf-114">Verwenden Sie zum Signieren einer Assembly beim Erstellen auf CoreCLR die Option [-keyfile](keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6bccf-114">To sign an assembly when building on CoreCLR, use the [-keyfile](keyfile-compiler-option.md) option.</span></span>
  
 <span data-ttu-id="6bccf-115">Wenn Sie mit der Option [-target:module](./target-module-compiler-option.md) kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, wenn Sie dieses Modul in eine Assembly mit [-addmodule](./addmodule-compiler-option.md) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6bccf-115">If you compile with [-target:module](./target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="6bccf-116">Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.</span><span class="sxs-lookup"><span data-stu-id="6bccf-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="6bccf-117">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keyfile](./keyfile-compiler-option.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="6bccf-117">You can also pass your encryption information to the compiler with [-keyfile](./keyfile-compiler-option.md).</span></span> <span data-ttu-id="6bccf-118">Verwenden Sie [-delaysign](./delaysign-compiler-option.md), wenn Sie den in das Assemblymanifest eingefügten Schlüssel verwenden, aber das Signieren der Assembly bis nach deren verzögern möchten, bis diese getestet wurde.</span><span class="sxs-lookup"><span data-stu-id="6bccf-118">Use [-delaysign](./delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="6bccf-119">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md) und [Verzögertes Signieren einer Assembly](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="6bccf-119">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6bccf-120">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="6bccf-120">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="6bccf-121">Diese Compileroption ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6bccf-121">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="6bccf-122">Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> programmgesteuert auf diese Compileroption zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6bccf-122">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bccf-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bccf-123">See also</span></span>

- [<span data-ttu-id="6bccf-124">C#-Compileroption „-keyfile“</span><span class="sxs-lookup"><span data-stu-id="6bccf-124">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="6bccf-125">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="6bccf-125">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="6bccf-126">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="6bccf-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
