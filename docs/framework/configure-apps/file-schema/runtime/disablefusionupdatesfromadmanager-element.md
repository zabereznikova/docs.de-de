---
title: <disableFusionUpdatesFromADManager>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1923e70143ea2a158447eccdb35d347fe4f51ea
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663767"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="6e7c4-102">\<disablefusionupdatesfromadmanager-> Element</span><span class="sxs-lookup"><span data-stu-id="6e7c4-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="6e7c4-103">Gibt an, ob das Standardverhalten deaktiviert wird. Dieses besteht darin, dem Laufzeithost das Außerkraftsetzen von Konfigurationseinstellungen für eine Anwendungsdomäne zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="6e7c4-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="6e7c4-104">\<configuration> Element</span></span>  
<span data-ttu-id="6e7c4-105">\<Runtime-> Element</span><span class="sxs-lookup"><span data-stu-id="6e7c4-105">\<runtime> Element</span></span>  
<span data-ttu-id="6e7c4-106">\<disableFusionUpdatesFromADManager></span><span class="sxs-lookup"><span data-stu-id="6e7c4-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e7c4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e7c4-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e7c4-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6e7c4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6e7c4-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e7c4-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6e7c4-110">Attributes</span></span>  
  
|<span data-ttu-id="6e7c4-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6e7c4-111">Attribute</span></span>|<span data-ttu-id="6e7c4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e7c4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e7c4-113">enabled</span><span class="sxs-lookup"><span data-stu-id="6e7c4-113">enabled</span></span>|<span data-ttu-id="6e7c4-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="6e7c4-115">Gibt an, ob die Standard Fähigkeit zum Überschreiben von Fusions Einstellungen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6e7c4-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="6e7c4-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="6e7c4-117">Wert</span><span class="sxs-lookup"><span data-stu-id="6e7c4-117">Value</span></span>|<span data-ttu-id="6e7c4-118">Description</span><span class="sxs-lookup"><span data-stu-id="6e7c4-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e7c4-119">0</span><span class="sxs-lookup"><span data-stu-id="6e7c4-119">0</span></span>|<span data-ttu-id="6e7c4-120">Deaktivieren Sie nicht die Möglichkeit, die Fusion-Einstellungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="6e7c4-121">Dies ist das Standardverhalten, beginnend mit dem .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-121">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="6e7c4-122">1</span><span class="sxs-lookup"><span data-stu-id="6e7c4-122">1</span></span>|<span data-ttu-id="6e7c4-123">Deaktivieren Sie die Möglichkeit zum Überschreiben von Fusion-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="6e7c4-124">Dadurch wird das Verhalten früherer Versionen des .NET Framework wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e7c4-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e7c4-125">Child Elements</span></span>  
 <span data-ttu-id="6e7c4-126">Keine</span><span class="sxs-lookup"><span data-stu-id="6e7c4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e7c4-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e7c4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6e7c4-128">Element</span><span class="sxs-lookup"><span data-stu-id="6e7c4-128">Element</span></span>|<span data-ttu-id="6e7c4-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e7c4-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6e7c4-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6e7c4-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e7c4-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e7c4-132">Remarks</span></span>  
 <span data-ttu-id="6e7c4-133">Beginnend mit dem .NET Framework 4 besteht das Standardverhalten darin, dass das <xref:System.AppDomainManager> -Objekt Konfigurationseinstellungen mithilfe der <xref:System.AppDomainSetup.ConfigurationFile%2A> -Eigenschaft <xref:System.AppDomainSetup> oder der <xref:System.AppDomainSetup.SetConfigurationBytes%2A> -Methode des-Objekts, das an die-Implementierung übermittelt wird, überschreiben kann. der- <xref:System.AppDomainManager>Methode in der Unterklasse von. <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6e7c4-133">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="6e7c4-134">Bei der Standard Anwendungsdomäne setzen die Einstellungen, die Sie ändern, die Einstellungen außer Kraft, die von der Anwendungs Konfigurationsdatei angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="6e7c4-135">Für andere Anwendungs Domänen überschreiben Sie die Konfigurationseinstellungen, die an die <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> - <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> Methode oder die-Methode übergebenen wurden.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="6e7c4-136">Sie können entweder neue Konfigurationsinformationen übergeben oder NULL (`Nothing` in Visual Basic) übergeben, um die übergebenen Konfigurationsinformationen auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="6e7c4-137">Übergeben Sie Konfigurationsinformationen nicht an die <xref:System.AppDomainSetup.ConfigurationFile%2A> -Eigenschaft und die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="6e7c4-138">Wenn Sie Konfigurationsinformationen an beides übergeben, werden die Informationen, die Sie <xref:System.AppDomainSetup.ConfigurationFile%2A> an die-Eigenschaft übergeben, <xref:System.AppDomainSetup.SetConfigurationBytes%2A> ignoriert, da die-Methode Konfigurationsinformationen aus der Anwendungs Konfigurationsdatei überschreibt.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="6e7c4-139"><xref:System.AppDomainSetup.ConfigurationFile%2A> Wenn Sie die-Eigenschaft verwenden, können Sie NULL (`Nothing` in Visual Basic) an die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> -Methode übergeben, um alle Konfigurations Bytes zu eliminieren, die im Aufrufe <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> der <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> -oder-Methode angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="6e7c4-140">Zusätzlich zu den Konfigurationsinformationen können Sie die <xref:System.AppDomainSetup> folgenden Einstellungen für das-Objekt ändern, das an die Implementierung <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> der-Methode weitergegeben <xref:System.AppDomainSetup.ApplicationBase%2A>wird <xref:System.AppDomainSetup.ApplicationName%2A>: <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> ,, , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, ,,<xref:System.AppDomainSetup.LoaderOptimization%2A>,, und<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>. <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.DynamicBase%2A> <xref:System.AppDomainSetup.ShadowCopyFiles%2A></span><span class="sxs-lookup"><span data-stu-id="6e7c4-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="6e7c4-141">Als Alternative zur Verwendung des `<disableFusionUpdatesFromADManager>` -Elements können Sie das Standardverhalten deaktivieren, indem Sie eine Registrierungs Einstellung erstellen oder eine Umgebungsvariable festlegen.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="6e7c4-142">Erstellen Sie in der Registrierung einen DWORD-Wert `COMPLUS_disableFusionUpdatesFromADManager` namens `HKCU\Software\Microsoft\.NETFramework` unter `HKLM\Software\Microsoft\.NETFramework`oder, und legen Sie den Wert auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="6e7c4-143">Legen Sie in der Befehlszeile die Umgebungsvariable `COMPLUS_disableFusionUpdatesFromADManager` auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e7c4-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e7c4-144">Example</span></span>  
 <span data-ttu-id="6e7c4-145">Das folgende Beispiel zeigt, wie Sie die Möglichkeit zum Überschreiben von Fusions Einstellungen mithilfe `<disableFusionUpdatesFromADManager>` des-Elements deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e7c4-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e7c4-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e7c4-146">See also</span></span>

- [<span data-ttu-id="6e7c4-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="6e7c4-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6e7c4-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="6e7c4-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6e7c4-149">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="6e7c4-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
