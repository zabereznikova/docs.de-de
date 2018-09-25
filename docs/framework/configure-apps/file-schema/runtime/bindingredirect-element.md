---
title: '&lt;BindingRedirect&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 535519c65aba7ce13703bb33a16b09cde84c3f03
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085550"
---
# <a name="ltbindingredirectgt-element"></a><span data-ttu-id="01b8a-102">&lt;BindingRedirect&gt; Element</span><span class="sxs-lookup"><span data-stu-id="01b8a-102">&lt;bindingRedirect&gt; Element</span></span>
<span data-ttu-id="01b8a-103">Leitet eine Assemblyversion in eine andere um.</span><span class="sxs-lookup"><span data-stu-id="01b8a-103">Redirects one assembly version to another.</span></span>  
  
 <span data-ttu-id="01b8a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="01b8a-104">\<configuration></span></span>  
<span data-ttu-id="01b8a-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="01b8a-105">\<runtime></span></span>  
<span data-ttu-id="01b8a-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="01b8a-106">\<assemblyBinding></span></span>  
<span data-ttu-id="01b8a-107">\<DependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="01b8a-107">\<dependentAssembly></span></span>  
<span data-ttu-id="01b8a-108">\<BindingRedirect ></span><span class="sxs-lookup"><span data-stu-id="01b8a-108">\<bindingRedirect></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b8a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="01b8a-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01b8a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="01b8a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="01b8a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="01b8a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01b8a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="01b8a-112">Attributes</span></span>  
  
|<span data-ttu-id="01b8a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="01b8a-113">Attribute</span></span>|<span data-ttu-id="01b8a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01b8a-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="01b8a-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="01b8a-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="01b8a-116">Gibt die Assemblyversion an, die ursprünglich angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="01b8a-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="01b8a-117">Hat das Format einer Assemblyversionsnummer *"Hauptversion.Nebenversion.Build.Revision"*.</span><span class="sxs-lookup"><span data-stu-id="01b8a-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="01b8a-118">Gültige Werte für jeden Abschnitt dieser Versionsnummer sind 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="01b8a-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="01b8a-119">Sie können auch einen Bereich an Versionsnummern angeben, und zwar im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="01b8a-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="01b8a-120">*n.n.n.n - n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="01b8a-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="01b8a-121">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="01b8a-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="01b8a-122">Gibt die Version der Assembly, die anstelle der ursprünglich angeforderten Version im Format verwendet: *n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="01b8a-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="01b8a-123">Dieser Wert kann eine frühere Version als `oldVersion` angeben.</span><span class="sxs-lookup"><span data-stu-id="01b8a-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01b8a-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01b8a-124">Child Elements</span></span>  
  
|<span data-ttu-id="01b8a-125">Element</span><span class="sxs-lookup"><span data-stu-id="01b8a-125">Element</span></span>|<span data-ttu-id="01b8a-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01b8a-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01b8a-127">Keiner</span><span class="sxs-lookup"><span data-stu-id="01b8a-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="01b8a-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01b8a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="01b8a-129">Element</span><span class="sxs-lookup"><span data-stu-id="01b8a-129">Element</span></span>|<span data-ttu-id="01b8a-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01b8a-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="01b8a-131">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="01b8a-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="01b8a-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="01b8a-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="01b8a-133">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="01b8a-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="01b8a-134">Verwenden Sie für jede Assembly ein dependentAssembly-Element.</span><span class="sxs-lookup"><span data-stu-id="01b8a-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="01b8a-135">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="01b8a-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01b8a-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01b8a-136">Remarks</span></span>  
 <span data-ttu-id="01b8a-137">Wenn Sie eine .NET Framework-Anwendung mit einer Assembly mit starkem Namen erstellen, verwendet die Anwendung zur Laufzeit standardmäßig diese Version der Assembly, selbst wenn eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="01b8a-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="01b8a-138">Sie können die Anwendung jedoch auch so konfigurieren, dass sie mit einer neueren Version der Assembly ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="01b8a-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="01b8a-139">Weitere Informationen darüber, wie die Runtime diese Dateien verwendet, um zu bestimmen, welche Assemblyversion verwenden, finden Sie unter [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="01b8a-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="01b8a-140">Sie können mehrere Assemblyversionen umleiten, indem Sie mehrere `bindingRedirect`-Elemente in ein `dependentAssembly`-Element aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="01b8a-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="01b8a-141">Sie können auch von einer neueren Version zu einer früheren Version der Assembly umleiten.</span><span class="sxs-lookup"><span data-stu-id="01b8a-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="01b8a-142">Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="01b8a-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="01b8a-143">Dies betrifft die Umleitung von .NET Framework-Assemblys und Assemblys von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="01b8a-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="01b8a-144">Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="01b8a-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="01b8a-145">Weitere Informationen finden Sie unter [Sicherheitsberechtigung für die Umleitung der Assemblybindung](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="01b8a-145">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01b8a-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01b8a-146">Example</span></span>  
 <span data-ttu-id="01b8a-147">Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten.</span><span class="sxs-lookup"><span data-stu-id="01b8a-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01b8a-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01b8a-148">See Also</span></span>  
 [<span data-ttu-id="01b8a-149">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="01b8a-149">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="01b8a-150">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="01b8a-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="01b8a-151">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="01b8a-151">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
