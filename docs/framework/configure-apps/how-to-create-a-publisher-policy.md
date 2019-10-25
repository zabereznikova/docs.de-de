---
title: 'Gewusst wie: Erstellen einer Herausgeberrichtlinie'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 608918828bf72369a1bd48e2391e2423078e9df0
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846836"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="b21dc-102">Gewusst wie: Erstellen einer Herausgeberrichtlinie</span><span class="sxs-lookup"><span data-stu-id="b21dc-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="b21dc-103">Anbieter von Assemblys können angeben, dass Anwendungen eine neuere Version einer Assembly verwenden sollen, indem Sie eine Herausgeber Richtlinien Datei mit der aktualisierten Assembly einschließen.</span><span class="sxs-lookup"><span data-stu-id="b21dc-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="b21dc-104">Die Herausgeber Richtlinien Datei gibt die Assemblyumleitung und die Code Basis Einstellungen an und verwendet das gleiche Format wie eine Anwendungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b21dc-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="b21dc-105">Die Herausgeber Richtlinien Datei wird in eine Assembly kompiliert und in den globalen Assemblycache eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b21dc-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="b21dc-106">Zum Erstellen einer Herausgeber Richtlinie sind drei Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b21dc-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="b21dc-107">Erstellen Sie eine Herausgeber Richtlinien Datei.</span><span class="sxs-lookup"><span data-stu-id="b21dc-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="b21dc-108">Erstellen Sie eine Herausgeber Richtlinien-Assembly.</span><span class="sxs-lookup"><span data-stu-id="b21dc-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="b21dc-109">Fügen Sie die Herausgeber Richtlinien-Assembly dem globalen Assemblycache hinzu</span><span class="sxs-lookup"><span data-stu-id="b21dc-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="b21dc-110">Das Schema für die Herausgeber Richtlinie wird unter [umleiten](redirect-assembly-versions.md)von Assemblyversionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b21dc-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="b21dc-111">Das folgende Beispiel zeigt eine Herausgeber Richtlinien Datei, die eine Version von `myAssembly` zu einer anderen umleitet.</span><span class="sxs-lookup"><span data-stu-id="b21dc-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="b21dc-112">Informationen zum Angeben einer Codebasis finden Sie unter [angeben des Speicher Orts einer Assembly](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="b21dc-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="b21dc-113">Erstellen der Herausgeber Richtlinien-Assembly</span><span class="sxs-lookup"><span data-stu-id="b21dc-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="b21dc-114">Verwenden Sie den [Assembly Linker (Al. exe)](../tools/al-exe-assembly-linker.md) , um die Herausgeber Richtlinien-Assembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b21dc-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="b21dc-115">So erstellen Sie eine Herausgeber Richtlinien-Assembly</span><span class="sxs-lookup"><span data-stu-id="b21dc-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="b21dc-116">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="b21dc-116">Type the following command at the command prompt:</span></span>

<span data-ttu-id="b21dc-117">**Al/Link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keypaarfile* **/Platform:** *ProcessorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="b21dc-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>

<span data-ttu-id="b21dc-118">In diesem Befehl:</span><span class="sxs-lookup"><span data-stu-id="b21dc-118">In this command:</span></span>

- <span data-ttu-id="b21dc-119">Das *publisherPolicyFile* -Argument ist der Name der Herausgeber Richtlinien Datei.</span><span class="sxs-lookup"><span data-stu-id="b21dc-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="b21dc-120">Das *publisherPolicyAssemblyFile* -Argument ist der Name der Herausgeber Richtlinienassembly, die sich aus diesem Befehl ergibt.</span><span class="sxs-lookup"><span data-stu-id="b21dc-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="b21dc-121">Der Assemblydateiname muss das folgende Format aufweisen:</span><span class="sxs-lookup"><span data-stu-id="b21dc-121">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="b21dc-122">**Policy.**</span><span class="sxs-lookup"><span data-stu-id="b21dc-122">**policy.**</span></span> <span data-ttu-id="b21dc-123">*majornumber* **.**</span><span class="sxs-lookup"><span data-stu-id="b21dc-123">*majorNumber* **.**</span></span> <span data-ttu-id="b21dc-124">*minornumber* **.**</span><span class="sxs-lookup"><span data-stu-id="b21dc-124">*minorNumber* **.**</span></span> <span data-ttu-id="b21dc-125">*MainAssemblyName* **. dll**</span><span class="sxs-lookup"><span data-stu-id="b21dc-125">*mainAssemblyName* **.dll**</span></span>

- <span data-ttu-id="b21dc-126">Das *keypairren File* -Argument ist der Name der Datei, die das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="b21dc-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="b21dc-127">Sie müssen die Assembly-und Herausgeber richtlinienassembly mit demselben Schlüsselpaar signieren.</span><span class="sxs-lookup"><span data-stu-id="b21dc-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="b21dc-128">Das *ProcessorArchitecture* -Argument identifiziert die Plattform, auf die eine prozessorspezifische Assembly abzielt.</span><span class="sxs-lookup"><span data-stu-id="b21dc-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b21dc-129">Die Möglichkeit, eine bestimmte Prozessorarchitektur als Ziel zu erreichen, ist ab .NET Framework 2,0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b21dc-129">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="b21dc-130">Die Möglichkeit, eine bestimmte Prozessorarchitektur als Ziel zu erreichen, ist ab .NET Framework 2,0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b21dc-130">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="b21dc-131">Der folgende Befehl erstellt eine Herausgeber richtlinienassembly namens `policy.1.0.myAssembly` aus einer Herausgeber Richtlinien Datei namens `pub.config`, weist der Assembly einen starken Namen zu, indem das Schlüsselpaar in der `sgKey.snk` Datei verwendet wird, und gibt an, dass die Assembly auf den x86-Prozessor ausgerichtet Architektur.</span><span class="sxs-lookup"><span data-stu-id="b21dc-131">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="b21dc-132">Die Herausgeber richtlinienassembly muss der Prozessorarchitektur der Assembly entsprechen, auf die Sie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b21dc-132">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="b21dc-133">Wenn die Assembly also den <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> Wert <xref:System.Reflection.ProcessorArchitecture.MSIL>aufweist, muss die Herausgeber richtlinienassembly für diese Assembly mit `/platform:anycpu`erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b21dc-133">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="b21dc-134">Sie müssen für jede prozessorspezifische Assembly eine separate Herausgeber richtlinienassembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b21dc-134">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="b21dc-135">Eine Folge dieser Regel besteht darin, dass Sie die Haupt-oder neben Komponente der Versionsnummer ändern müssen, damit Sie eine neue Herausgeber richtlinienassembly mit der richtigen Prozessorarchitektur bereitstellen können, um die Prozessorarchitektur für eine Assembly zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b21dc-135">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="b21dc-136">Die alte Herausgeber richtlinienassembly kann die Assembly nicht bedienen, wenn die Assembly über eine andere Prozessorarchitektur verfügt.</span><span class="sxs-lookup"><span data-stu-id="b21dc-136">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="b21dc-137">Eine weitere Konsequenz besteht darin, dass der Linker der Version 2,0 nicht verwendet werden kann, um eine Herausgeber richtlinienassembly für eine Assembly zu erstellen, die mit früheren Versionen der .NET Framework kompiliert wurde</span><span class="sxs-lookup"><span data-stu-id="b21dc-137">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="b21dc-138">Hinzufügen der Herausgeber Richtlinien-Assembly zum globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="b21dc-138">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="b21dc-139">Verwenden Sie das [Global Assembly Cache-Tool (Gacutil. exe)](../tools/gacutil-exe-gac-tool.md) , um die Herausgeber richtlinienassembly dem globalen Assemblycache hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b21dc-139">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="b21dc-140">So fügen Sie die Herausgeber Richtlinien-Assembly dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="b21dc-140">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="b21dc-141">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="b21dc-141">Type the following command at the command prompt:</span></span>

<span data-ttu-id="b21dc-142">**gacutil/i**  *publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="b21dc-142">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>

<span data-ttu-id="b21dc-143">Der folgende Befehl fügt dem globalen Assemblycache `policy.1.0.myAssembly.dll` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b21dc-143">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="b21dc-144">Die Herausgeber richtlinienassembly kann nicht zum globalen Assemblycache hinzugefügt werden, es sei denn, die ursprüngliche Herausgeber Richtlinien Datei befindet sich im selben Verzeichnis wie die</span><span class="sxs-lookup"><span data-stu-id="b21dc-144">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="b21dc-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b21dc-145">See also</span></span>

- [<span data-ttu-id="b21dc-146">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="b21dc-146">Programming with Assemblies</span></span>](../../standard/assembly/program.md)
- [<span data-ttu-id="b21dc-147">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="b21dc-147">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="b21dc-148">Konfigurieren von apps mithilfe von Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b21dc-148">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="b21dc-149">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b21dc-149">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="b21dc-150">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b21dc-150">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="b21dc-151">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="b21dc-151">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
