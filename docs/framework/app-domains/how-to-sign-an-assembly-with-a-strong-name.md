---
title: 'Vorgehensweise: Signieren einer Assembly mit einem starken Namen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bd250caae1bd98d238f8d99702a97f0cdbc7448
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826901"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="5991e-102">Vorgehensweise: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="5991e-102">How to: Sign an Assembly with a Strong Name</span></span>
<span data-ttu-id="5991e-103">Es gibt mehrere Möglichkeiten, eine Assembly mit einem starken Namen zu signieren:</span><span class="sxs-lookup"><span data-stu-id="5991e-103">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
-   <span data-ttu-id="5991e-104">Mithilfe der Registerkarte **Signierung** im Dialogfeld **Eigenschaften** eines Projekts in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5991e-104">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="5991e-105">Dies ist die einfachste und bequemste Methode, eine Assembly mit einem starken Namen zu signieren.</span><span class="sxs-lookup"><span data-stu-id="5991e-105">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
-   <span data-ttu-id="5991e-106">Mit dem [Assemblylinker-Tool (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) , um ein .NET Framework-Codemodul (eine NETMODULE-Datei) mit einer Schlüsseldatei zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="5991e-106">By using the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a .netmodule file) with a key file.</span></span>  
  
-   <span data-ttu-id="5991e-107">Mithilfe von Assemblyattributen, um die Informationen zum starken Namen in den Code einzufügen.</span><span class="sxs-lookup"><span data-stu-id="5991e-107">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="5991e-108">Abhängig von dem Ort, an dem sich die zu verwendende Schlüsseldatei befindet, können Sie entweder das <xref:System.Reflection.AssemblyKeyFileAttribute> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="5991e-108">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
-   <span data-ttu-id="5991e-109">Mithilfe von Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="5991e-109">By using compiler options.</span></span>  
  
 <span data-ttu-id="5991e-110">Sie benötigen ein kryptografisches Schlüsselpaar, um eine Assembly mit einem starken Namen zu signieren.</span><span class="sxs-lookup"><span data-stu-id="5991e-110">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="5991e-111">Weitere Informationen zum Erstellen eines Schlüsselpaars finden Sie unter [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="5991e-111">For more information about creating a key pair, see [How to: Create a Public-Private Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="5991e-112">So erstellen und signieren Sie eine Assembly mit einem starken Namen mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5991e-112">To create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1.  <span data-ttu-id="5991e-113">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="5991e-113">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="5991e-114">Wählen Sie die Registerkarte **Signierung** aus.</span><span class="sxs-lookup"><span data-stu-id="5991e-114">Choose the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="5991e-115">Wählen Sie das Feld **Assembly signieren** aus.</span><span class="sxs-lookup"><span data-stu-id="5991e-115">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="5991e-116">Wählen Sie im Feld **Schlüsseldatei mit starkem Namen auswählen** die Option **\<Durchsuchen…>** aus, und navigieren Sie dann zur Schlüsseldatei.</span><span class="sxs-lookup"><span data-stu-id="5991e-116">In the **Choose a strong name key file** box, choose **\<Browse…>**, and then navigate to the key file.</span></span> <span data-ttu-id="5991e-117">Wählen Sie zum Erstellen einer neuen Schlüsseldatei **\<Neu…>** aus, und geben Sie ihren Namen im Dialogfeld **Schlüssel für einen starken Namen erstellen** ein.</span><span class="sxs-lookup"><span data-stu-id="5991e-117">To create a new key file, choose **\<New…>** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5991e-118">Wählen Sie eine Datei mit öffentlichem Schlüssel aus, um [die Signierung einer Assembly zu verzögern](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="5991e-118">In order to [delay sign an assembly](../../../docs/framework/app-domains/delay-sign-assembly.md), choose a public key file.</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="5991e-119">So erstellen und signieren Sie eine Assembly mit einem starken Namen unter Verwendung des Assemblylinkers</span><span class="sxs-lookup"><span data-stu-id="5991e-119">To create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
-   <span data-ttu-id="5991e-120">Geben Sie an der [Developer-Eingabeaufforderung für Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="5991e-120">At the [Developer Command Prompt for Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="5991e-121">**al** **/out:**\<*Assemblyname*> *\<Modulname>* **/keyfile:**\<*Schlüsseldateiname*></span><span class="sxs-lookup"><span data-stu-id="5991e-121">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  
  
     <span data-ttu-id="5991e-122">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="5991e-122">where:</span></span>  
  
     <span data-ttu-id="5991e-123">*assemblyName*</span><span class="sxs-lookup"><span data-stu-id="5991e-123">*assemblyName*</span></span>  
     <span data-ttu-id="5991e-124">Der Name der stark signierten Assembly (eine DLL- oder EXE-Datei), die der Assemblylinker ausgibt.</span><span class="sxs-lookup"><span data-stu-id="5991e-124">The name of the strongly signed assembly (a .dll or .exe file) that Assembly Linker will emit.</span></span>  
  
     <span data-ttu-id="5991e-125">*moduleName*</span><span class="sxs-lookup"><span data-stu-id="5991e-125">*moduleName*</span></span>  
     <span data-ttu-id="5991e-126">Der Name eines .NET Framework-Codemoduls (eine NETMODULE-Datei), das mindestens einen Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="5991e-126">The name of a .NET Framework code module (a .netmodule file) that includes one or more types.</span></span> <span data-ttu-id="5991e-127">Sie können eine NETMODULE-Datei erstellen, indem Sie Code mit dem Schalter `/target:module` in C# oder Visual Basic kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5991e-127">You can create a .netmodule file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>  
  
     <span data-ttu-id="5991e-128">*keyfileName*</span><span class="sxs-lookup"><span data-stu-id="5991e-128">*keyfileName*</span></span>  
     <span data-ttu-id="5991e-129">Der Name des Containers oder der Datei, der bzw. die das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="5991e-129">The name of the container or file that contains the key pair.</span></span> <span data-ttu-id="5991e-130">Assemblylinker interpretiert einen relativen Pfad in Beziehung zum aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5991e-130">Assembly Linker interprets a relative path in relationship to the current directory.</span></span>  
  
 <span data-ttu-id="5991e-131">Im folgenden Beispiel wird die Assembly `MyAssembly.dll` unter Verwendung der Schlüsseldatei `sgKey.snk`mit einem starken Namen signiert.</span><span class="sxs-lookup"><span data-stu-id="5991e-131">The following example signs the assembly `MyAssembly.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 <span data-ttu-id="5991e-132">Weitere Informationen über die Verwendung dieses Tools finden Sie unter [Assemblylinker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="5991e-132">For more information about this tool, see [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
#### <a name="to-sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="5991e-133">So signieren Sie eine Assembly mit einem starken Namen unter Verwendung von Attributen</span><span class="sxs-lookup"><span data-stu-id="5991e-133">To sign an assembly with a strong name by using attributes</span></span>  
  
1.  <span data-ttu-id="5991e-134">Fügen Sie in Ihrer Codemoduldatei das <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut hinzu, und geben Sie den Namen der Datei oder des Containers an, die bzw. der das zum Signieren der Assembly mit einem starken Namen zu verwendende Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="5991e-134">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  
  
2.  <span data-ttu-id="5991e-135">Kompilieren Sie die Quellcodedatei normal.</span><span class="sxs-lookup"><span data-stu-id="5991e-135">Compile the source code file normally.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5991e-136">Die C#- und Visual Basic-Compiler geben Compilerwarnungen aus (CS1699 bzw. BC41008), wenn das <xref:System.Reflection.AssemblyKeyFileAttribute> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut im Quellcode auftreten.</span><span class="sxs-lookup"><span data-stu-id="5991e-136">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="5991e-137">Sie können die Warnungen ignorieren.</span><span class="sxs-lookup"><span data-stu-id="5991e-137">You can ignore the warnings.</span></span>  
  
 <span data-ttu-id="5991e-138">Im folgenden Beispiel wird das <xref:System.Reflection.AssemblyKeyFileAttribute> -Attribut mit der Schlüsseldatei `keyfile.snk`verwendet, die sich in dem Verzeichnis befindet, in dem die Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="5991e-138">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called `keyfile.snk`, which is located in the directory where the assembly is compiled.</span></span>  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
 <span data-ttu-id="5991e-139">Sie können auch während des Kompiliervorgangs der Quelldatei eine Assembly verzögert signieren.</span><span class="sxs-lookup"><span data-stu-id="5991e-139">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="5991e-140">Weitere Informationen finden Sie unter [Verzögertes Signieren einer Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="5991e-140">For more information, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="5991e-141">So signieren Sie eine Assembly mit einem starken Namen unter Verwendung des Compilers</span><span class="sxs-lookup"><span data-stu-id="5991e-141">To sign an assembly with a strong name by using the compiler</span></span>  
  
-   <span data-ttu-id="5991e-142">Kompilieren Sie Ihre Quellcodedateien mit der Compileroption `/keyfile` oder `/delaysign` in C# und Visual Basic bzw. mit der Linkeroption `/KEYFILE` oder `/DELAYSIGN` in C++.</span><span class="sxs-lookup"><span data-stu-id="5991e-142">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="5991e-143">Fügen Sie nach dem Optionsnamen einen Doppelpunkt und den Namen der Schlüsseldatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5991e-143">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="5991e-144">Wenn Sie einen Befehlszeilencompiler verwenden, können Sie die Schlüsseldatei in das Verzeichnis kopieren, das die Quellcodedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="5991e-144">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  
  
     <span data-ttu-id="5991e-145">Informationen zum verzögerten Signieren finden Sie unter [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="5991e-145">For information on delay signing, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
     <span data-ttu-id="5991e-146">Im folgenden Beispiel wird der C#-Compiler verwendet und die Assembly `UtilityLibrary.dll` mithilfe der Schlüsseldatei `sgKey.snk` mit einem starken Namen signiert.</span><span class="sxs-lookup"><span data-stu-id="5991e-146">The following example uses the C# compiler and signs the assembly `UtilityLibrary.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5991e-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5991e-147">See also</span></span>
- [<span data-ttu-id="5991e-148">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="5991e-148">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="5991e-149">Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars</span><span class="sxs-lookup"><span data-stu-id="5991e-149">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [<span data-ttu-id="5991e-150">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="5991e-150">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="5991e-151">Verzögertes Signieren einer Assembly</span><span class="sxs-lookup"><span data-stu-id="5991e-151">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)
- [<span data-ttu-id="5991e-152">Verwalten der Signierung von Assemblys und Manifesten</span><span class="sxs-lookup"><span data-stu-id="5991e-152">Managing Assembly and Manifest Signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [<span data-ttu-id="5991e-153">Seite „Signierung“, Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="5991e-153">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
