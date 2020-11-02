---
title: Festlegen von Assemblyattributen
description: Sie können Assemblyattribute für eine .NET-Assembly festlegen einschließlich Assemblyidentität, Informationen, Assemblymanifest und Attributen für starke Namen.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 32318d647dee8f3f397e3497e7c2da640bd492d0
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687686"
---
# <a name="set-assembly-attributes"></a><span data-ttu-id="c0816-103">Festlegen von Assemblyattributen</span><span class="sxs-lookup"><span data-stu-id="c0816-103">Set assembly attributes</span></span>

<span data-ttu-id="c0816-104">Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0816-104">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="c0816-105">Die Attribute sind in die folgenden Gruppen von Informationen unterteilt:</span><span class="sxs-lookup"><span data-stu-id="c0816-105">The attributes are divided into the following sets of information:</span></span>

- <span data-ttu-id="c0816-106">Attribute für Assemblyidentitäten</span><span class="sxs-lookup"><span data-stu-id="c0816-106">Assembly identity attributes</span></span>

- <span data-ttu-id="c0816-107">Informationsattribute</span><span class="sxs-lookup"><span data-stu-id="c0816-107">Informational attributes</span></span>

- <span data-ttu-id="c0816-108">Attribute für Assemblymanifeste.</span><span class="sxs-lookup"><span data-stu-id="c0816-108">Assembly manifest attributes</span></span>

- <span data-ttu-id="c0816-109">Attribute für starke Namen</span><span class="sxs-lookup"><span data-stu-id="c0816-109">Strong name attributes</span></span>

## <a name="assembly-identity-attributes"></a><span data-ttu-id="c0816-110">Attribute für Assemblyidentitäten</span><span class="sxs-lookup"><span data-stu-id="c0816-110">Assembly identity attributes</span></span>

<span data-ttu-id="c0816-111">Drei Attribute bestimmen zusammen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: "name", "version" und "culture".</span><span class="sxs-lookup"><span data-stu-id="c0816-111">Three attributes, together with a strong name (if applicable), determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="c0816-112">Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c0816-112">These attributes form the full name of the assembly and are required when referencing the assembly in code.</span></span> <span data-ttu-id="c0816-113">Mit Attributen können die Version und Kultur einer Assembly festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c0816-113">You can use attributes to set an assembly's version and culture.</span></span> <span data-ttu-id="c0816-114">Der Compiler oder der [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) legt beim Erstellen der Assembly den Namenswert auf Grundlage der Datei fest, die das Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="c0816-114">The compiler or the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) sets the name value when the assembly is created, based on the file containing the assembly manifest.</span></span>

<span data-ttu-id="c0816-115">In der folgenden Tabelle werden das version- und das culture-Attribut beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0816-115">The following table describes the version and culture attributes.</span></span>

|<span data-ttu-id="c0816-116">Attribut für Assemblyidentität</span><span class="sxs-lookup"><span data-stu-id="c0816-116">Assembly identity attribute</span></span>|<span data-ttu-id="c0816-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0816-117">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="c0816-118">Ein aufgelistetes Feld, das die von der Assembly unterstützte Kultur angibt.</span><span class="sxs-lookup"><span data-stu-id="c0816-118">Enumerated field indicating the culture that the assembly supports.</span></span> <span data-ttu-id="c0816-119">Eine Assembly kann auch eine Kulturunabhängigkeit angeben. In diesem Fall enthält sie die Ressourcen für die Standardkultur.</span><span class="sxs-lookup"><span data-stu-id="c0816-119">An assembly can also specify culture independence, indicating that it contains the resources for the default culture.</span></span> <span data-ttu-id="c0816-120">**Hinweis** :  Die Runtime behandelt jede Assembly, für die das culture-Attribut nicht auf NULL festgelegt ist, als Satellitenassembly.</span><span class="sxs-lookup"><span data-stu-id="c0816-120">**Note:**  The runtime treats any assembly that does not have the culture attribute set to null as a satellite assembly.</span></span> <span data-ttu-id="c0816-121">Solche Assemblys unterliegen den Bindungsregeln für Satellitenassemblys.</span><span class="sxs-lookup"><span data-stu-id="c0816-121">Such assemblies are subject to satellite assembly binding rules.</span></span> <span data-ttu-id="c0816-122">Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="c0816-122">For more information, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="c0816-123">Ein Wert, der Assemblyattribute festlegt, etwa ob die Assembly parallel ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0816-123">Value that sets assembly attributes, such as whether the assembly can be run side by side.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="c0816-124">Ein numerischer Wert mit dem Format *Haupt* . *Neben* . *Build* . *Revision* (z. B. 2.4.0.0).</span><span class="sxs-lookup"><span data-stu-id="c0816-124">Numeric value in the format *major* . *minor* . *build* . *revision* (for example, 2.4.0.0).</span></span> <span data-ttu-id="c0816-125">Common Language Runtime verwendet diesen Wert zum Durchführen von Bindungsvorgängen in Assemblys mit der Eigenschaft "Starker Name".</span><span class="sxs-lookup"><span data-stu-id="c0816-125">The common language runtime uses this value to perform binding operations in strong-named assemblies.</span></span> <span data-ttu-id="c0816-126">**Hinweis** :  Wenn das <xref:System.Reflection.AssemblyInformationalVersionAttribute>-Attribut nicht auf eine Assembly angewendet wird, wird die Versionsnummer, die vom <xref:System.Reflection.AssemblyVersionAttribute>-Attribut angegeben wird, von den Eigenschaften <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0816-126">**Note:**  If the <xref:System.Reflection.AssemblyInformationalVersionAttribute> attribute is not applied to an assembly, the version number specified by the <xref:System.Reflection.AssemblyVersionAttribute> attribute is used by the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>, and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|

<span data-ttu-id="c0816-127">Im folgenden Codebeispiel wird veranschaulicht, wie das version- und das culture-Attribut auf eine Assembly angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0816-127">The following code example shows how to apply the version and culture attributes to an assembly.</span></span>

```cpp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")];
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")];
```

```csharp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")]
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")]
```

```vb
' Set version number for the assembly.
<Assembly:AssemblyVersionAttribute("4.3.2.1")>
' Set culture as German.
<Assembly:AssemblyCultureAttribute("de")>
```

## <a name="informational-attributes"></a><span data-ttu-id="c0816-128">Informationsattribute</span><span class="sxs-lookup"><span data-stu-id="c0816-128">Informational attributes</span></span>

<span data-ttu-id="c0816-129">Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0816-129">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="c0816-130">Die folgende Tabelle beschreibt die verschiedenen Informationsattribute, die auf eine Assembly angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c0816-130">The following table describes the informational attributes you can apply to an assembly.</span></span>

|<span data-ttu-id="c0816-131">Informationsattribut</span><span class="sxs-lookup"><span data-stu-id="c0816-131">Informational attribute</span></span>|<span data-ttu-id="c0816-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0816-132">Description</span></span>|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="c0816-133">Ein Zeichenfolgenwert, der einen Firmennamen angibt.</span><span class="sxs-lookup"><span data-stu-id="c0816-133">String value specifying a company name.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="c0816-134">Ein Zeichenfolgenwert, der Copyright-Informationen angibt.</span><span class="sxs-lookup"><span data-stu-id="c0816-134">String value specifying copyright information.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="c0816-135">Ein Zeichenfolgenwert, der die Win32-Dateiversionsnummer angibt.</span><span class="sxs-lookup"><span data-stu-id="c0816-135">String value specifying the Win32 file version number.</span></span> <span data-ttu-id="c0816-136">Dies ist normalerweise standardmäßig die Assemblyversion.</span><span class="sxs-lookup"><span data-stu-id="c0816-136">This normally defaults to the assembly version.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="c0816-137">Ein Zeichenfolgenwert, der Versionsinformationen angibt, die zur Laufzeit nicht verwendet werden (zum Beispiel die vollständige Produktversionsnummer).</span><span class="sxs-lookup"><span data-stu-id="c0816-137">String value specifying version information that is not used by the common language runtime, such as a full product version number.</span></span> <span data-ttu-id="c0816-138">**Hinweis** :  Wenn dieses Attribut auf eine Assembly angewendet wird, kann die davon angegebene Zeichenfolge zur Laufzeit mithilfe der <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>-Eigenschaft abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c0816-138">**Note:**  If this attribute is applied to an assembly, the string it specifies can be obtained at run time by using the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="c0816-139">Diese Zeichenfolge wird auch im von den Eigenschaften <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> bereitgestellten Pfad und Registrierungsschlüssel verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0816-139">The string is also used in the path and registry key provided by the <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="c0816-140">Ein Zeichenfolgenwert, der Produktinformationen angibt.</span><span class="sxs-lookup"><span data-stu-id="c0816-140">String value specifying product information.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="c0816-141">Ein Zeichenfolgenwert, der Markeninformationen angibt.</span><span class="sxs-lookup"><span data-stu-id="c0816-141">String value specifying trademark information.</span></span>|

<span data-ttu-id="c0816-142">Diese Attribute können auf der Windows-Eigenschaftenseite der Assembly angezeigt werden, oder sie können mithilfe der **/win32res** -Compileroption überschrieben werden, um Ihre eigene Win32-Ressourcendatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c0816-142">These attributes can appear on the Windows Properties page of the assembly, or they can be overridden using the **/win32res** compiler option to specify your own Win32 resource file.</span></span>

## <a name="assembly-manifest-attributes"></a><span data-ttu-id="c0816-143">Attribute für Assemblymanifeste.</span><span class="sxs-lookup"><span data-stu-id="c0816-143">Assembly manifest attributes</span></span>

<span data-ttu-id="c0816-144">Mit Attributen für Assemblymanifeste können Informationen im Assemblymanifest angegeben werden, einschließlich Titel, Beschreibung, Standardalias und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c0816-144">You can use assembly manifest attributes to provide information in the assembly manifest, including title, description, the default alias, and configuration.</span></span> <span data-ttu-id="c0816-145">In der folgenden Tabelle werden die Attribute für Assemblymanifeste beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0816-145">The following table describes the assembly manifest attributes.</span></span>

|<span data-ttu-id="c0816-146">Attribut für Assemblymanifeste</span><span class="sxs-lookup"><span data-stu-id="c0816-146">Assembly manifest attribute</span></span>|<span data-ttu-id="c0816-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0816-147">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="c0816-148">Ein Zeichenfolgenwert, der die Assemblykonfiguration angibt, beispielsweise "Einzelhandel" oder "Debuggen".</span><span class="sxs-lookup"><span data-stu-id="c0816-148">String value indicating the configuration of the assembly, such as Retail or Debug.</span></span> <span data-ttu-id="c0816-149">Dieser Wert wird zur Laufzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0816-149">The runtime does not use this value.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="c0816-150">Ein Zeichenfolgenwert, der einen Standardalias angibt, der von Assemblys mit einem Verweis verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0816-150">String value specifying a default alias to be used by referencing assemblies.</span></span> <span data-ttu-id="c0816-151">Dieser Wert stellt einen Anzeigenamen zur Verfügung, wenn der eigentliche Name der Assembly nicht angezeigt wird (zum Beispiel ein GUID-Wert).</span><span class="sxs-lookup"><span data-stu-id="c0816-151">This value provides a friendly name when the name of the assembly itself is not friendly (such as a GUID value).</span></span> <span data-ttu-id="c0816-152">Dieser Wert kann auch als Kurzform des vollen Assemblynamens verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0816-152">This value can also be used as a short form of the full assembly name.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="c0816-153">Ein Zeichenfolgenwert, der eine kurze Beschreibung angibt, die Natur und Zweck der Assembly zusammenfasst.</span><span class="sxs-lookup"><span data-stu-id="c0816-153">String value specifying a short description that summarizes the nature and purpose of the assembly.</span></span>|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="c0816-154">Ein Zeichenfolgenwert, der einen Anzeigenamen für die Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="c0816-154">String value specifying a friendly name for the assembly.</span></span> <span data-ttu-id="c0816-155">Beispielsweise kann eine Assembly mit dem Namen *comdlg* den Titel „Microsoft Common Dialog Control“ (Allgemeines Microsoft-Dialogsteuerelement) haben.</span><span class="sxs-lookup"><span data-stu-id="c0816-155">For example, an assembly named *comdlg* might have the title Microsoft Common Dialog Control.</span></span>|

## <a name="strong-name-attributes"></a><span data-ttu-id="c0816-156">Attribute für starke Namen</span><span class="sxs-lookup"><span data-stu-id="c0816-156">Strong name attributes</span></span>

<span data-ttu-id="c0816-157">Sie können Attribute für starke Namen verwenden, um einen starken Namen für eine Assembly festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c0816-157">You can use strong name attributes to set a strong name for an assembly.</span></span> <span data-ttu-id="c0816-158">In der folgenden Tabelle werden die Attribute für starke Namen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0816-158">The following table describes the strong name attributes.</span></span>

|<span data-ttu-id="c0816-159">Attribut für starke Namen</span><span class="sxs-lookup"><span data-stu-id="c0816-159">Strong name attribute</span></span>|<span data-ttu-id="c0816-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0816-160">Description</span></span>|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|<span data-ttu-id="c0816-161">Ein boolescher Wert, der angibt, dass die verzögerte Signierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="c0816-161">Boolean value indicating that delay signing is being used.</span></span>|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|<span data-ttu-id="c0816-162">Ein Zeichenfolgenwert, der den Namen der Datei angibt, die entweder den öffentlichen Schlüssel (bei verzögerter Signierung) oder öffentliche und private Schlüssel enthält, die an den Konstruktor dieses Attributs als Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0816-162">String value indicating the name of the file that contains either the public key (if using delay signing) or both the public and private keys passed as a parameter to the constructor of this attribute.</span></span> <span data-ttu-id="c0816-163">Beachten Sie, dass der Dateiname relativ zum Pfad der Ausgabedatei ist (die *EXE* - oder *DLL* -Datei) und nicht zum Pfad der Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="c0816-163">Note that the file name is relative to the output file path (the *.exe* or *.dll* ), not the source file path.</span></span>|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|<span data-ttu-id="c0816-164">Zeigt den Schlüsselcontainer an, der das Schlüsselpaar enthält, das an den Konstruktor dieses Attributs als Parameter übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c0816-164">Indicates the key container that contains the key pair passed as a parameter to the constructor of this attribute.</span></span>|

<span data-ttu-id="c0816-165">Das folgende Codebeispiel zeigt die Attribute, die angewendet werden, wenn mithilfe der verzögerten Signierung eine Assembly mit starkem Namen mit einer Datei des öffentlichen Schlüssels *myKey.snk* erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c0816-165">The following code example shows the attributes to apply when using delay signing to create a strong-named assembly with a public key file called *myKey.snk* .</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c0816-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0816-166">See also</span></span>

- [<span data-ttu-id="c0816-167">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="c0816-167">Create assemblies</span></span>](create.md)
