---
title: Verzögertes Signieren einer Assembly
description: In diesem Artikel wird die verzögerte oder partielle Signierung beschrieben, die in der PE-Datei Speicherplatz für die Signatur mit dem starken Namen reserviert, aber die tatsächliche Signatur verzögert.
ms.date: 08/19/2019
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 704ddbec3ddd179622fdc7289036247763449256
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162894"
---
# <a name="delay-sign-an-assembly"></a><span data-ttu-id="13447-103">Verzögertes Signieren einer Assembly</span><span class="sxs-lookup"><span data-stu-id="13447-103">Delay-sign an assembly</span></span>

<span data-ttu-id="13447-104">Organisationen können ein streng geheim gehaltenes Schlüsselpaar verwenden, auf das Entwickler nicht täglich zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="13447-104">An organization can have a closely guarded key pair that developers can't access on a daily basis.</span></span> <span data-ttu-id="13447-105">Der öffentliche Schlüssel stünde zur Verfügung, während der Zugriff auf den privaten Schlüssel nur einigen Wenigen erlaubt wäre.</span><span class="sxs-lookup"><span data-stu-id="13447-105">The public key is often available, but access to the private key is restricted to only a few individuals.</span></span> <span data-ttu-id="13447-106">Beim Entwickeln von Assemblys mit starken Namen enthält jede Assembly, die auf die Zielassembly mit dem starken Namen verweist, das Token des öffentlichen Schlüssels, mit dem der starke Name der Zielassembly erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="13447-106">When developing assemblies with strong names, each assembly that references the strong-named target assembly contains the token of the public key used to give the target assembly a strong name.</span></span> <span data-ttu-id="13447-107">Aus diesem Grund muss der öffentliche Schlüssel während des Entwicklungsprozesses verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="13447-107">This requires that the public key be available during the development process.</span></span>

<span data-ttu-id="13447-108">Mit dem verzögerten Signieren oder dem Teilsignieren zur Buildzeit können Sie Speicherplatz in der portierbaren ausführbaren Datei (Portable Executable, PE) für die Signatur mit starkem Namen reservieren, das eigentliche Signieren aber auf einen späteren Zeitpunkt verschieben, i.d.R. unmittelbar vor der Weitergabe der Assembly.</span><span class="sxs-lookup"><span data-stu-id="13447-108">You can use delayed or partial signing at build time to reserve space in the portable executable (PE) file for the strong name signature, but defer the actual signing until some later stage, usually just before shipping the assembly.</span></span>

<span data-ttu-id="13447-109">So verzögern Sie das Signieren einer Assembly:</span><span class="sxs-lookup"><span data-stu-id="13447-109">To delay-sign an assembly:</span></span>

1. <span data-ttu-id="13447-110">Holen Sie sich den öffentlichen Schlüssel des Schlüsselpaars von der Organisation, die letztendlich signieren wird.</span><span class="sxs-lookup"><span data-stu-id="13447-110">Get the public key portion of the key pair from the organization that will do the eventual signing.</span></span> <span data-ttu-id="13447-111">In der Regel liegt dieser Schlüssel in Form einer *SNK*-Datei vor, die mit dem vom Windows SDK bereitgestellten [Strong Name-Tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="13447-111">Typically this key is in the form of an *.snk* file, which can be created using the [Strong Name tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) provided by the Windows SDK.</span></span>

2. <span data-ttu-id="13447-112">Kommentieren Sie den Quellcode für die Assembly mit den zwei benutzerdefinierten Attribute aus <xref:System.Reflection>:</span><span class="sxs-lookup"><span data-stu-id="13447-112">Annotate the source code for the assembly with two custom attributes from <xref:System.Reflection>:</span></span>

   - <span data-ttu-id="13447-113"><xref:System.Reflection.AssemblyKeyFileAttribute>, das den Namen der Datei mit dem öffentlichen Schlüssel als Parameter an den Konstruktor übergibt</span><span class="sxs-lookup"><span data-stu-id="13447-113"><xref:System.Reflection.AssemblyKeyFileAttribute>, which passes the name of the file containing the public key as a parameter to its constructor.</span></span>

   - <span data-ttu-id="13447-114"><xref:System.Reflection.AssemblyDelaySignAttribute>, das angibt, dass beim verzögerten Signieren **TRUE** als Parameter an den Konstruktor übergeben wird</span><span class="sxs-lookup"><span data-stu-id="13447-114"><xref:System.Reflection.AssemblyDelaySignAttribute>, which indicates that delay signing is being used by passing **true** as a parameter to its constructor.</span></span>

   <span data-ttu-id="13447-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="13447-115">For example:</span></span>

   ```cpp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")];
   [assembly:AssemblyDelaySignAttribute(true)];
   ```

   ```csharp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")]
   [assembly:AssemblyDelaySignAttribute(true)]
   ```

   ```vb
   <Assembly:AssemblyKeyFileAttribute("myKey.snk")>
   <Assembly:AssemblyDelaySignAttribute(True)>
   ```

3. <span data-ttu-id="13447-116">Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und reserviert in der PE-Datei Speicherplatz für die vollständige Signatur mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="13447-116">The compiler inserts the public key into the assembly manifest and reserves space in the PE file for the full strong name signature.</span></span> <span data-ttu-id="13447-117">Der echte öffentliche Schlüssel muss während der Erstellung der Assembly gespeichert werden, damit andere Assemblys, die auf diese Assembly verweisen, den Schlüssel abrufen und in ihrem eigenen Assemblyverweis speichern können.</span><span class="sxs-lookup"><span data-stu-id="13447-117">The real public key must be stored while the assembly is built so that other assemblies that reference this assembly can obtain the key to store in their own assembly reference.</span></span>

4. <span data-ttu-id="13447-118">Da die Assembly über keine gültige Signatur mit starkem Namen verfügt, muss die Überprüfung der Signatur deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="13447-118">Because the assembly does not have a valid strong name signature, the verification of that signature must be turned off.</span></span> <span data-ttu-id="13447-119">Dies erreichen Sie mit der Option **–Vr** im Strong Name-Tool.</span><span class="sxs-lookup"><span data-stu-id="13447-119">You can do this by using the **–Vr** option with the Strong Name tool.</span></span>

     <span data-ttu-id="13447-120">Das folgende Beispiel deaktiviert die Überprüfung für eine Assembly namens *myAssembly.dll*.</span><span class="sxs-lookup"><span data-stu-id="13447-120">The following example turns off verification for an assembly called *myAssembly.dll*.</span></span>

   ```console
   sn –Vr myAssembly.dll
   ```

   <span data-ttu-id="13447-121">Wenn Sie die Überprüfung auf Plattformen wie Advanced RISC Machine-Mikroprozessoren (ARM) deaktivieren möchten, auf denen das Strong Name-Tool nicht ausgeführt werden kann, erstellen Sie mit der Option **–Vk** eine Registrierungsdatei.</span><span class="sxs-lookup"><span data-stu-id="13447-121">To turn off verification on platforms where you can't run the Strong Name tool, such as Advanced RISC Machine (ARM) microprocessors, use the **–Vk** option to create a registry file.</span></span> <span data-ttu-id="13447-122">Importieren Sie die Registrierungsdatei in die Registrierung des Computers, auf dem die Überprüfung deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="13447-122">Import the registry file into the registry on the computer where you want to turn off verification.</span></span> <span data-ttu-id="13447-123">Im folgenden Beispiel wird eine Registrierungsdatei für `myAssembly.dll` erstellt.</span><span class="sxs-lookup"><span data-stu-id="13447-123">The following example creates a registry file for `myAssembly.dll`.</span></span>

   ```console
   sn –Vk myRegFile.reg myAssembly.dll
   ```

   <span data-ttu-id="13447-124">Mit den Optionen **–Vr** oder **–Vk** lässt sich optional eine *SNK*-Datei zum Testen der Schlüsselsignatur einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="13447-124">With either the **–Vr** or **–Vk** option, you can optionally include an *.snk* file for test key signing.</span></span>

   > [!WARNING]
   > <span data-ttu-id="13447-125">Verlassen Sie sich für die Sicherheit nicht auf starke Namen.</span><span class="sxs-lookup"><span data-stu-id="13447-125">Do not rely on strong names for security.</span></span> <span data-ttu-id="13447-126">Diese Namen bieten lediglich eine eindeutige Identität.</span><span class="sxs-lookup"><span data-stu-id="13447-126">They provide a unique identity only.</span></span>

   > [!NOTE]
   > <span data-ttu-id="13447-127">Wenn Sie während der Entwicklung mit Visual Studio auf einem 64-Bit-Computer das verzögerte Signieren verwenden und eine Assembly für **Any CPU** (Beliebige CPU) kompilieren, müssen Sie die Option **-Vr** möglicherweise zweimal anwenden.</span><span class="sxs-lookup"><span data-stu-id="13447-127">If you use delay signing during development with Visual Studio on a 64-bit computer, and you compile an assembly for **Any CPU**, you might have to apply the **-Vr** option twice.</span></span> <span data-ttu-id="13447-128">In Visual Studio ist **Beliebige CPU** der Wert der Buildeigenschaft **Zielplattform**. Wenn Sie über die Befehlszeile kompilieren, ist dies der Standardwert. Um Ihre Anwendung über die Befehlszeile oder über den Datei-Explorer auszuführen, nutzen Sie die 64-Bit-Version von [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md), um die Option **-Vr** auf die Assembly anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="13447-128">(In Visual Studio, **Any CPU** is a value of the **Platform Target** build property; when you compile from the command line, it is the default.) To run your application from the command line or from File Explorer, use the 64-bit version of the [Sn.exe (Strong Name tool)](../../framework/tools/sn-exe-strong-name-tool.md) to apply the **-Vr** option to the assembly.</span></span> <span data-ttu-id="13447-129">Wenn Sie die Assembly zur Entwurfszeit in Visual Studio laden möchten (z.B., wenn die Assembly Komponenten enthält, die von anderen Assemblys in Ihrer Anwendung verwendet werden), verwenden Sie die 32-Bit-Version des Strong Name-Tools.</span><span class="sxs-lookup"><span data-stu-id="13447-129">To load the assembly into Visual Studio at design time (for example, if the assembly contains components that are used by other assemblies in your application), use the 32-bit version of the strong-name tool.</span></span> <span data-ttu-id="13447-130">Dies ist notwendig, weil der Just-in-Time-Compiler (JIT) die Assembly in nativem 64-Bit-Code kompiliert, wenn die Assembly über die Befehlszeile ausgeführt wird, und in nativem 32-Bit-Code, wenn die Assembly in die Entwurfszeitumgebung geladen wird.</span><span class="sxs-lookup"><span data-stu-id="13447-130">This is because the just-in-time (JIT) compiler compiles the assembly to 64-bit native code when the assembly is run from the command line, and to 32-bit native code when the assembly is loaded into the design-time environment.</span></span>

5. <span data-ttu-id="13447-131">Zu einem späteren Zeitpunkt – in der Regel vor der Weitergabe der Assembly – übergeben Sie die Assembly an die Signierungsstelle Ihrer Organisation, um sie mit der Option **–R** und dem Strong Name-Tool mit starkem Namen signieren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="13447-131">Later, usually just before shipping, you submit the assembly to your organization's signing authority for the actual strong name signing using the **–R** option with the Strong Name tool.</span></span>

   <span data-ttu-id="13447-132">Im folgenden Beispiel wird eine Assembly namens *myAssembly.dll*, die das *sgKey.snk*-Schlüsselpaar enthält, mit starkem Namen signiert.</span><span class="sxs-lookup"><span data-stu-id="13447-132">The following example signs an assembly called *myAssembly.dll* with a strong name using the *sgKey.snk* key pair.</span></span>

   ```console
   sn -R myAssembly.dll sgKey.snk
   ```

## <a name="see-also"></a><span data-ttu-id="13447-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13447-133">See also</span></span>

- [<span data-ttu-id="13447-134">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="13447-134">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="13447-135">How to: Erstellen eines öffentlichen/privaten Schlüsselpaars</span><span class="sxs-lookup"><span data-stu-id="13447-135">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="13447-136">Sn.exe (Strong Name-Tool)</span><span class="sxs-lookup"><span data-stu-id="13447-136">Sn.exe (Strong Name tool)</span></span>](../../framework/tools/sn-exe-strong-name-tool.md)
