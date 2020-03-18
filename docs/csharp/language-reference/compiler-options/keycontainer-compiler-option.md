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
ms.openlocfilehash: fead2d4296cfa6fb0195cb4b43f6448c0fc7e6a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970140"
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="83063-102">-keycontainer (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="83063-102">-keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="83063-103">Gibt den Namen des kryptografischen Schlüsselcontainers an.</span><span class="sxs-lookup"><span data-stu-id="83063-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83063-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83063-104">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="83063-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="83063-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="83063-106">Der Name des Containers mit dem Schlüssel für einen starken Namen</span><span class="sxs-lookup"><span data-stu-id="83063-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83063-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83063-107">Remarks</span></span>  
 <span data-ttu-id="83063-108">Wenn die Option **-keycontainer** verwendet wird, erstellt der Compiler eine teilbare Komponente.</span><span class="sxs-lookup"><span data-stu-id="83063-108">When the **-keycontainer** option is used, the compiler creates a sharable component.</span></span> <span data-ttu-id="83063-109">Der Compiler fügt einen öffentlichen Schlüssel vom angegebenen Container in das Assemblymanifest ein und signiert die endgültige Assembly mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="83063-109">The compiler inserts a public key from the specified container into the assembly manifest and signs the final assembly with the private key.</span></span> <span data-ttu-id="83063-110">Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="83063-110">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="83063-111">`sn -i` installiert das Schlüsselpaar im Container.</span><span class="sxs-lookup"><span data-stu-id="83063-111">`sn -i` installs the key pair into a container.</span></span> <span data-ttu-id="83063-112">Diese Option wird nicht unterstützt, wenn der Compiler auf CoreCLR ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="83063-112">This option is not supported when the compiler runs on CoreCLR.</span></span> <span data-ttu-id="83063-113">Verwenden Sie zum Signieren einer Assembly beim Erstellen auf CoreCLR die Option [-keyfile](keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="83063-113">To sign an assembly when building on CoreCLR, use the [-keyfile](keyfile-compiler-option.md) option.</span></span>
  
 <span data-ttu-id="83063-114">Wenn Sie mit der Option [-target:module](./target-module-compiler-option.md) kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, wenn Sie dieses Modul in eine Assembly mit [-addmodule](./addmodule-compiler-option.md) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="83063-114">If you compile with [-target:module](./target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="83063-115">Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.</span><span class="sxs-lookup"><span data-stu-id="83063-115">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="83063-116">Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keyfile](./keyfile-compiler-option.md) an den Compiler übergeben.</span><span class="sxs-lookup"><span data-stu-id="83063-116">You can also pass your encryption information to the compiler with [-keyfile](./keyfile-compiler-option.md).</span></span> <span data-ttu-id="83063-117">Verwenden Sie [-delaysign](./delaysign-compiler-option.md), wenn Sie den in das Assemblymanifest eingefügten Schlüssel verwenden, aber das Signieren der Assembly bis nach deren verzögern möchten, bis diese getestet wurde.</span><span class="sxs-lookup"><span data-stu-id="83063-117">Use [-delaysign](./delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="83063-118">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md) und [Verzögertes Signieren einer Assembly](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="83063-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="83063-119">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="83063-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="83063-120">Diese Compileroption ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83063-120">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="83063-121">Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> programmgesteuert auf diese Compileroption zugreifen.</span><span class="sxs-lookup"><span data-stu-id="83063-121">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83063-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83063-122">See also</span></span>

- [<span data-ttu-id="83063-123">C#-Compileroption „-keyfile“</span><span class="sxs-lookup"><span data-stu-id="83063-123">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="83063-124">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="83063-124">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="83063-125">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="83063-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
