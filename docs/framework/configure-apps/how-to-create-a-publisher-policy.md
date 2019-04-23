---
title: 'Vorgehensweise: Erstellen einer Herausgeberrichtlinie'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: ce2df9d4cea601652ebde2032758137b01faacdc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344662"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="ef743-102">Vorgehensweise: Erstellen einer Herausgeberrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ef743-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="ef743-103">Anbieter von Assemblys können angeben, dass Anwendungen auf eine neuere Version einer Assembly verwenden sollen, dazu eine Herausgeberrichtlinien-Datei mit der aktualisierten Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="ef743-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="ef743-104">Die Herausgeberrichtliniendatei gibt Assemblyumleitungen und Code-Basis-Einstellungen, und verwendet das gleiche Format wie eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ef743-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="ef743-105">Die Herausgeberrichtliniendatei ist in eine Assembly kompiliert und im globalen Assemblycache platziert.</span><span class="sxs-lookup"><span data-stu-id="ef743-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="ef743-106">Es gibt drei Schritte zum Erstellen einer Herausgeberrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="ef743-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1. <span data-ttu-id="ef743-107">Erstellen Sie eine Herausgeberrichtlinien-Datei.</span><span class="sxs-lookup"><span data-stu-id="ef743-107">Create a publisher policy file.</span></span>  
  
2. <span data-ttu-id="ef743-108">Erstellen Sie eine Herausgeberrichtlinienassembly an.</span><span class="sxs-lookup"><span data-stu-id="ef743-108">Create a publisher policy assembly.</span></span>  
  
3. <span data-ttu-id="ef743-109">Fügen Sie der Herausgeberrichtlinienassembly im globalen Assemblycache hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef743-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="ef743-110">Das Schema für die Herausgeberrichtlinie wird beschrieben, [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="ef743-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="ef743-111">Das folgende Beispiel zeigt einen Verleger Richtliniendatei, die eine Version der leitet `myAssembly` in einen anderen.</span><span class="sxs-lookup"><span data-stu-id="ef743-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
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
  
 <span data-ttu-id="ef743-112">Gewusst wie: angeben eine Codebasis finden Sie unter [angeben des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="ef743-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="ef743-113">Erstellen der Herausgeberrichtlinienassembly</span><span class="sxs-lookup"><span data-stu-id="ef743-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="ef743-114">Verwenden der [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) die Herausgeberrichtlinienassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef743-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="ef743-115">Zum Erstellen der Herausgeberrichtlinienassembly</span><span class="sxs-lookup"><span data-stu-id="ef743-115">To create a publisher policy assembly</span></span>  
  
1. <span data-ttu-id="ef743-116">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="ef743-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="ef743-117">**Al/Link:** *PublisherPolicyFile* **/out:** *PublisherPolicyAssemblyFile* **/keyfile:**  *KeyPairFile* **/Platform:** *ProcessorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="ef743-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="ef743-118">In diesem Befehl:</span><span class="sxs-lookup"><span data-stu-id="ef743-118">In this command:</span></span>  
  
    -   <span data-ttu-id="ef743-119">Die *PublisherPolicyFile* -Argument ist der Name der Herausgeberrichtliniendatei.</span><span class="sxs-lookup"><span data-stu-id="ef743-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="ef743-120">Die *PublisherPolicyAssemblyFile* Argument ist der Name der Herausgeberrichtlinienassembly an, die durch diesen Befehl entsteht.</span><span class="sxs-lookup"><span data-stu-id="ef743-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="ef743-121">Der Assemblyname für die Datei muss Folgendes Format aufweisen:</span><span class="sxs-lookup"><span data-stu-id="ef743-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="ef743-122">**die Richtlinie.**</span><span class="sxs-lookup"><span data-stu-id="ef743-122">**policy.**</span></span> <span data-ttu-id="ef743-123">*MajorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="ef743-123">*majorNumber* **.**</span></span> <span data-ttu-id="ef743-124">*MinorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="ef743-124">*minorNumber* **.**</span></span> <span data-ttu-id="ef743-125">*mainAssemblyName* **.dll**</span><span class="sxs-lookup"><span data-stu-id="ef743-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="ef743-126">Die *KeyPairFile* Argument ist der Name der Datei mit dem Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="ef743-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="ef743-127">Sie müssen die Assembly und der Herausgeberrichtlinienassembly mit dem gleichen Schlüsselpaar anmelden.</span><span class="sxs-lookup"><span data-stu-id="ef743-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="ef743-128">Die *ProcessorArchitecture* Argument identifiziert die Plattform, die von einer Assembly macht prozessorspezifische.</span><span class="sxs-lookup"><span data-stu-id="ef743-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ef743-129">Die Möglichkeit, eine bestimmte Prozessorarchitektur ist neu in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="ef743-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="ef743-130">Der folgende Befehl erstellt eine Herausgeberrichtlinienassembly namens `policy.1.0.myAssembly` über eine Herausgeberrichtliniendatei aufgerufen `pub.config`, weist einen starken Namen der Assembly, die mit dem Schlüsselpaar in der `sgKey.snk` Datei, und gibt an, dass die Assembly der X86 ausgerichtet ist. Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="ef743-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="ef743-131">Die Herausgeberrichtlinienassembly muss die Prozessorarchitektur der Assembly übereinstimmen, die er zutrifft.</span><span class="sxs-lookup"><span data-stu-id="ef743-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="ef743-132">Daher verfügt die Assembly eine <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> Wert <xref:System.Reflection.ProcessorArchitecture.MSIL>, die Herausgeberrichtlinienassembly für diese Assembly muss erstellt werden, mit `/platform:anycpu`.</span><span class="sxs-lookup"><span data-stu-id="ef743-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="ef743-133">Sie müssen eine Separate bereitstellen Herausgeberrichtlinienassembly für jede Assembly macht prozessorspezifische.</span><span class="sxs-lookup"><span data-stu-id="ef743-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="ef743-134">Diese Regel hat zur Folge, um die Prozessorarchitektur für eine Assembly zu ändern, die Haupt- oder Nebenversion-Komponente, der die Versionsnummer ändern müssen, damit Sie eine neue Herausgeberrichtlinienassembly mit die richtige Prozessorarchitektur angeben können.</span><span class="sxs-lookup"><span data-stu-id="ef743-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="ef743-135">Die alte Herausgeberrichtlinienassembly kann nicht Ihre Assembly Dienst, sobald die Assembly über eine andere Prozessorarchitektur aufweist.</span><span class="sxs-lookup"><span data-stu-id="ef743-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="ef743-136">Ein weitere Konsequenz ist der Version 2.0-Linker kann nicht verwendet werden, zum Erstellen der Herausgeberrichtlinienassembly für eine Assembly kompiliert mit früheren Versionen von .NET Framework, da sie immer die Prozessorarchitektur angibt.</span><span class="sxs-lookup"><span data-stu-id="ef743-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="ef743-137">Hinzufügen der Herausgeberrichtlinienassembly im globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="ef743-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="ef743-138">Verwenden der [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) der Herausgeberrichtlinienassembly im globalen Assemblycache hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef743-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="ef743-139">Der Herausgeberrichtlinienassembly im globalen Assemblycache hinzu</span><span class="sxs-lookup"><span data-stu-id="ef743-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1. <span data-ttu-id="ef743-140">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="ef743-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="ef743-141">\**Gacutil/i\*\*\*PublisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="ef743-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="ef743-142">Der folgende Befehl fügt `policy.1.0.myAssembly.dll` im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="ef743-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ef743-143">Die Herausgeberrichtlinienassembly kann nicht im globalen Assemblycache hinzugefügt werden, es sei denn, die ursprüngliche Herausgeberrichtlinien-Datei im gleichen Verzeichnis wie die Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="ef743-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef743-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef743-144">See also</span></span>

- [<span data-ttu-id="ef743-145">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="ef743-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="ef743-146">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="ef743-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="ef743-147">Konfigurieren von Apps mithilfe von Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="ef743-147">Configuring Apps by using Configuration Files</span></span>](../../../docs/framework/configure-apps/index.md)
- [<span data-ttu-id="ef743-148">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ef743-148">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ef743-149">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ef743-149">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ef743-150">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="ef743-150">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
