---
title: 'Gewusst wie: Erstellen einer Herausgeberrichtlinie'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 182882d33772054c7ac4208ca9571fa8018c2a07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="fdc29-102">Gewusst wie: Erstellen einer Herausgeberrichtlinie</span><span class="sxs-lookup"><span data-stu-id="fdc29-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="fdc29-103">Anbieter von Assemblys können der Status, Anwendungen auf eine neuere Version einer Assembly verwenden soll, indem Sie z. B. eine Herausgeberrichtlinien-Datei mit der aktualisierten Assembly.</span><span class="sxs-lookup"><span data-stu-id="fdc29-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="fdc29-104">Die Herausgeberrichtliniendatei gibt Assemblyumleitung und CodeBase-Einstellungen Code und verwendet das gleiche Format wie eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fdc29-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="fdc29-105">Die Herausgeberrichtliniendatei wird in eine Assembly kompiliert und im globalen Assemblycache platziert.</span><span class="sxs-lookup"><span data-stu-id="fdc29-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="fdc29-106">Erstellen einer Herausgeberrichtlinie umfasst drei Schritte:</span><span class="sxs-lookup"><span data-stu-id="fdc29-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1.  <span data-ttu-id="fdc29-107">Erstellen Sie eine Herausgeberrichtliniendatei.</span><span class="sxs-lookup"><span data-stu-id="fdc29-107">Create a publisher policy file.</span></span>  
  
2.  <span data-ttu-id="fdc29-108">Erstellen Sie eine Herausgeberrichtlinienassembly.</span><span class="sxs-lookup"><span data-stu-id="fdc29-108">Create a publisher policy assembly.</span></span>  
  
3.  <span data-ttu-id="fdc29-109">Fügen Sie die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdc29-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="fdc29-110">Das Schema für Herausgeberrichtlinien wird beschrieben, [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="fdc29-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="fdc29-111">Das folgende Beispiel zeigt einen Verleger Richtliniendatei, die eine Version der leitet `myAssembly` in eine andere.</span><span class="sxs-lookup"><span data-stu-id="fdc29-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="fdc29-112">Gewusst wie: angeben eine Codebasis finden Sie unter [angeben des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="fdc29-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="fdc29-113">Erstellen der Herausgeberrichtlinienassembly</span><span class="sxs-lookup"><span data-stu-id="fdc29-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="fdc29-114">Verwenden der [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) die Herausgeberrichtlinienassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fdc29-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="fdc29-115">So erstellen eine Herausgeberrichtlinienassembly</span><span class="sxs-lookup"><span data-stu-id="fdc29-115">To create a publisher policy assembly</span></span>  
  
1.  <span data-ttu-id="fdc29-116">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="fdc29-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="fdc29-117">**Al/Link:** *PublisherPolicyFile* **/out:** *PublisherPolicyAssemblyFile* **/keyfile:**  *KeyPairFile* **/Platform:** *ProcessorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="fdc29-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="fdc29-118">In diesem Befehl:</span><span class="sxs-lookup"><span data-stu-id="fdc29-118">In this command:</span></span>  
  
    -   <span data-ttu-id="fdc29-119">Die *PublisherPolicyFile* Argument ist der Name des der Herausgeberrichtliniendatei.</span><span class="sxs-lookup"><span data-stu-id="fdc29-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="fdc29-120">Die *PublisherPolicyAssemblyFile* -Argument ist der Name der Herausgeberrichtlinienassembly an, die durch diesen Befehl entsteht.</span><span class="sxs-lookup"><span data-stu-id="fdc29-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="fdc29-121">Der Dateiname der Assembly muss Folgendes Format aufweisen:</span><span class="sxs-lookup"><span data-stu-id="fdc29-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="fdc29-122">**Richtlinie.**</span><span class="sxs-lookup"><span data-stu-id="fdc29-122">**policy.**</span></span> <span data-ttu-id="fdc29-123">*MajorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="fdc29-123">*majorNumber* **.**</span></span> <span data-ttu-id="fdc29-124">*MinorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="fdc29-124">*minorNumber* **.**</span></span> <span data-ttu-id="fdc29-125">*MainAssemblyName* **DLL**</span><span class="sxs-lookup"><span data-stu-id="fdc29-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="fdc29-126">Die *KeyPairFile* -Argument ist der Name der Datei, die das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="fdc29-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="fdc29-127">Sie müssen die Assembly und die Herausgeberrichtlinienassembly mit dem gleichen Schlüsselpaar anmelden.</span><span class="sxs-lookup"><span data-stu-id="fdc29-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="fdc29-128">Die *ProcessorArchitecture* Argument identifiziert die Plattform, die auf eine Assembly prozessorspezifische.</span><span class="sxs-lookup"><span data-stu-id="fdc29-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fdc29-129">Die Möglichkeit, eine bestimmte Prozessorarchitektur ist neu in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="fdc29-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="fdc29-130">Der folgende Befehl erstellt eine Herausgeberrichtlinienassembly aufgerufen `policy.1.0.myAssembly` eine Herausgeberrichtliniendatei aufgerufen `pub.config`, weist einen starken Namen auf die Assembly mit dem Schlüsselpaar in der `sgKey.snk` Datei, und gibt an, dass die Assembly der X86 ausgerichtet ist. Architektur des Prozessors.</span><span class="sxs-lookup"><span data-stu-id="fdc29-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="fdc29-131">Die Herausgeberrichtlinienassembly muss die Prozessorarchitektur der Assembly übereinstimmen, die er gilt.</span><span class="sxs-lookup"><span data-stu-id="fdc29-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="fdc29-132">Daher verfügt die Assembly ein <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> Wert <xref:System.Reflection.ProcessorArchitecture.MSIL>, die Herausgeberrichtlinienassembly für diese Assembly muss erstellt werden, mit `/platform:anycpu`.</span><span class="sxs-lookup"><span data-stu-id="fdc29-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="fdc29-133">Geben Sie eine Separate Herausgeberrichtlinienassembly für jede prozessorspezifische Assembly.</span><span class="sxs-lookup"><span data-stu-id="fdc29-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="fdc29-134">Eine Folge von dieser Regel ist, um die Prozessorarchitektur für eine Assembly zu ändern, die Komponente Haupt- oder Nebenversion der Versionsnummer geändert werden muss, damit Sie eine neue Herausgeberrichtlinienassembly mit der richtigen Prozessorarchitektur bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="fdc29-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="fdc29-135">Die alte Herausgeberrichtlinienassembly Ihre Assembly nicht verarbeitet werden, sobald die Assembly über eine andere Prozessorarchitektur aufweist.</span><span class="sxs-lookup"><span data-stu-id="fdc29-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="fdc29-136">Ein weitere Konsequenz ist, dass der Linker Version 2.0 verwendet werden kann, erstellen Sie eine Herausgeberrichtlinienassembly für eine Assembly, die mit früheren Versionen von .NET Framework kompiliert, da sie immer die Prozessorarchitektur angibt.</span><span class="sxs-lookup"><span data-stu-id="fdc29-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="fdc29-137">Hinzufügen der Herausgeberrichtlinienassembly zum globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="fdc29-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="fdc29-138">Verwenden der [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fdc29-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="fdc29-139">So fügen Sie die Herausgeberrichtlinienassembly im globalen Assemblycache hinzu</span><span class="sxs-lookup"><span data-stu-id="fdc29-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1.  <span data-ttu-id="fdc29-140">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="fdc29-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="fdc29-141">**Gacutil/i***PublisherPolicyAssemblyFile* </span><span class="sxs-lookup"><span data-stu-id="fdc29-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="fdc29-142">Der folgende Befehl fügt `policy.1.0.myAssembly.dll` im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="fdc29-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fdc29-143">Die Herausgeberrichtlinienassembly kann nicht im globalen Assemblycache hinzugefügt werden, es sei denn, die ursprünglichen Herausgeberrichtlinien-Datei im gleichen Verzeichnis wie die Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="fdc29-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc29-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdc29-144">See Also</span></span>  
 [<span data-ttu-id="fdc29-145">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="fdc29-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="fdc29-146">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="fdc29-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="fdc29-147">Konfigurieren von Apps</span><span class="sxs-lookup"><span data-stu-id="fdc29-147">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="fdc29-148">Konfigurieren von .NET Framework-Apps</span><span class="sxs-lookup"><span data-stu-id="fdc29-148">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [<span data-ttu-id="fdc29-149">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="fdc29-149">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="fdc29-150">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="fdc29-150">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="fdc29-151">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="fdc29-151">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
