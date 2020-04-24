---
title: 'Vorgehensweise: Erstellen einer Herausgeberrichtlinie'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646061"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="223c7-102">Vorgehensweise: Erstellen einer Herausgeberrichtlinie</span><span class="sxs-lookup"><span data-stu-id="223c7-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="223c7-103">Anbieter von Assemblys können angeben, dass Anwendungen eine neuere Version einer Assembly verwenden sollten, indem sie eine Herausgeberrichtliniendatei in die aktualisierte Assembly einschließen.</span><span class="sxs-lookup"><span data-stu-id="223c7-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="223c7-104">Die Herausgeberrichtliniendatei gibt Assemblyumleitungs- und Codebasiseinstellungen an und verwendet das gleiche Format wie eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="223c7-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="223c7-105">Die Herausgeberrichtliniendatei wird in eine Assembly kompiliert und im globalen Assemblycache abgelegt.</span><span class="sxs-lookup"><span data-stu-id="223c7-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="223c7-106">Beim Erstellen einer Herausgeberrichtlinie sind drei Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="223c7-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="223c7-107">Erstellen Sie eine Publisher-Richtliniendatei.</span><span class="sxs-lookup"><span data-stu-id="223c7-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="223c7-108">Erstellen Sie eine Herausgeberrichtlinienassembly.</span><span class="sxs-lookup"><span data-stu-id="223c7-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="223c7-109">Fügen Sie die Herausgeberrichtlinienassembly dem globalen Assemblycache hinzu.</span><span class="sxs-lookup"><span data-stu-id="223c7-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="223c7-110">Das Schema für die Herausgeberrichtlinie wird unter [Umleiten von Assemblyversionen](redirect-assembly-versions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="223c7-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="223c7-111">Das folgende Beispiel zeigt eine Herausgeberrichtliniendatei, `myAssembly` die eine Version von einer anderen umleitet.</span><span class="sxs-lookup"><span data-stu-id="223c7-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="223c7-112">Informationen zum Angeben einer Codebasis finden Sie unter [Angeben des Speicherorts einer Assembly](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="223c7-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="223c7-113">Erstellen der Publisher-Richtlinienassembly</span><span class="sxs-lookup"><span data-stu-id="223c7-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="223c7-114">Verwenden Sie den [Assemblylinker (Al.exe),](../tools/al-exe-assembly-linker.md) um die Herausgeberrichtlinienassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="223c7-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="223c7-115">So erstellen Sie eine Herausgeberrichtlinienassembly</span><span class="sxs-lookup"><span data-stu-id="223c7-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="223c7-116">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="223c7-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="223c7-117">In diesem Befehl:</span><span class="sxs-lookup"><span data-stu-id="223c7-117">In this command:</span></span>

- <span data-ttu-id="223c7-118">Das `publisherPolicyFile` Argument ist der Name der Herausgeberrichtliniendatei.</span><span class="sxs-lookup"><span data-stu-id="223c7-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="223c7-119">Das `publisherPolicyAssemblyFile` Argument ist der Name der Herausgeberrichtlinienassembly, die sich aus diesem Befehl ergibt.</span><span class="sxs-lookup"><span data-stu-id="223c7-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="223c7-120">Der Assemblydateiname muss dem Folgenden folgen:</span><span class="sxs-lookup"><span data-stu-id="223c7-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="223c7-121">'policy.majorNumber.minorNumber.mainAssemblyName.dll'</span><span class="sxs-lookup"><span data-stu-id="223c7-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="223c7-122">Das `keyPairFile` Argument ist der Name der Datei, die das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="223c7-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="223c7-123">Sie müssen die Assembly- und Herausgeberrichtlinienassembly mit demselben Schlüsselpaar signieren.</span><span class="sxs-lookup"><span data-stu-id="223c7-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="223c7-124">Das `processorArchitecture` Argument identifiziert die Plattform, auf die eine prozessorspezifische Assembly abzielt.</span><span class="sxs-lookup"><span data-stu-id="223c7-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="223c7-125">Die Möglichkeit, auf eine bestimmte Prozessorarchitektur zu zielen, ist ab .NET Framework 2.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="223c7-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="223c7-126">Die Möglichkeit, auf eine bestimmte Prozessorarchitektur zu zielen, ist ab .NET Framework 2.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="223c7-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="223c7-127">Mit dem folgenden Befehl wird `policy.1.0.myAssembly` eine Herausgeberrichtlinienassembly `pub.config`erstellt, die aus einer Herausgeberrichtliniendatei namens `sgKey.snk` aufgerufen wird, der Assembly mithilfe des Schlüsselpaars in der Datei einen starken Namen zuweist und angibt, dass die Assembly auf die x86-Prozessorarchitektur abzielt.</span><span class="sxs-lookup"><span data-stu-id="223c7-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="223c7-128">Die Herausgeberrichtlinienassembly muss mit der Prozessorarchitektur der Assembly übereinstimmen, auf die sie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="223c7-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="223c7-129">Wenn Ihre Assembly den <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> Wert <xref:System.Reflection.ProcessorArchitecture.MSIL>von hat, muss daher die `/platform:anycpu`Herausgeberrichtlinienassembly für diese Assembly mit erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="223c7-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="223c7-130">Sie müssen für jede prozessorspezifische Assembly eine separate Herausgeberrichtlinienassembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="223c7-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="223c7-131">Diese Regel hat zur Folge, dass Sie zum Ändern der Prozessorarchitektur für eine Assembly die Haupt- oder Nebenkomponente der Versionsnummer ändern müssen, damit Sie eine neue Herausgeberrichtlinienassembly mit der richtigen Prozessorarchitektur bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="223c7-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="223c7-132">Die alte Herausgeberrichtlinienassembly kann Ihre Assembly nicht mehr bedienen, wenn die Assembly über eine andere Prozessorarchitektur verfügt.</span><span class="sxs-lookup"><span data-stu-id="223c7-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="223c7-133">Eine weitere Folge ist, dass der Linker version 2.0 nicht zum Erstellen einer Herausgeberrichtlinienassembly für eine Assembly verwendet werden kann, die mit früheren Versionen von .NET Framework kompiliert wurde, da er immer die Prozessorarchitektur angibt.</span><span class="sxs-lookup"><span data-stu-id="223c7-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="223c7-134">Hinzufügen der Publisher-Richtlinienassembly zum globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="223c7-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="223c7-135">Verwenden Sie das [Werkzeug Globaler Assemblycache (Gacutil.exe),](../tools/gacutil-exe-gac-tool.md) um die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="223c7-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="223c7-136">So fügen Sie die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzu</span><span class="sxs-lookup"><span data-stu-id="223c7-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="223c7-137">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="223c7-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="223c7-138">Der folgende `policy.1.0.myAssembly.dll` Befehl wird dem globalen Assemblycache hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="223c7-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="223c7-139">Die Herausgeberrichtlinienassembly kann dem globalen Assemblycache nur hinzugefügt werden, `/link` wenn sich die im Argument angegebene ursprüngliche Herausgeberrichtliniendatei im selben Verzeichnis wie die Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="223c7-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="223c7-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="223c7-140">See also</span></span>

- [<span data-ttu-id="223c7-141">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="223c7-141">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="223c7-142">So sucht die Laufzeit Assemblys</span><span class="sxs-lookup"><span data-stu-id="223c7-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="223c7-143">Konfigurieren von Apps mithilfe von Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="223c7-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="223c7-144">Laufzeiteinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="223c7-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="223c7-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="223c7-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="223c7-146">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="223c7-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
