---
title: <bindingRedirect>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: d96585b397f75dcb9fac7e7fce93799cc95e7c6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154295"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="afc6b-102">\<bindingRedirect> Element</span><span class="sxs-lookup"><span data-stu-id="afc6b-102">\<bindingRedirect> Element</span></span>
<span data-ttu-id="afc6b-103">Leitet eine Assemblyversion in eine andere um.</span><span class="sxs-lookup"><span data-stu-id="afc6b-103">Redirects one assembly version to another.</span></span>  
  
<span data-ttu-id="afc6b-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="afc6b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="afc6b-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="afc6b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="afc6b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<AssemblyBinding>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="afc6b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="afc6b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="afc6b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="afc6b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**</span><span class="sxs-lookup"><span data-stu-id="afc6b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afc6b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="afc6b-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afc6b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="afc6b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="afc6b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="afc6b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afc6b-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="afc6b-112">Attributes</span></span>  
  
|<span data-ttu-id="afc6b-113">attribute</span><span class="sxs-lookup"><span data-stu-id="afc6b-113">Attribute</span></span>|<span data-ttu-id="afc6b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afc6b-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="afc6b-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="afc6b-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="afc6b-116">Gibt die Assemblyversion an, die ursprünglich angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="afc6b-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="afc6b-117">Das Format einer Assemblyversionsnummer ist *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="afc6b-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="afc6b-118">Gültige Werte für jeden Abschnitt dieser Versionsnummer sind 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="afc6b-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="afc6b-119">Sie können auch einen Bereich an Versionsnummern angeben, und zwar im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="afc6b-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="afc6b-120">*n.n.n.n - n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="afc6b-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="afc6b-121">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="afc6b-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="afc6b-122">Gibt die Version der Assembly an, die anstelle der ursprünglich angeforderten Version im Format *n.n.n.n* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="afc6b-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="afc6b-123">Dieser Wert kann eine frühere Version als `oldVersion` angeben.</span><span class="sxs-lookup"><span data-stu-id="afc6b-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afc6b-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="afc6b-124">Child Elements</span></span>  
  
|<span data-ttu-id="afc6b-125">Element</span><span class="sxs-lookup"><span data-stu-id="afc6b-125">Element</span></span>|<span data-ttu-id="afc6b-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afc6b-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="afc6b-127">Keine</span><span class="sxs-lookup"><span data-stu-id="afc6b-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="afc6b-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="afc6b-128">Parent Elements</span></span>  
  
|<span data-ttu-id="afc6b-129">Element</span><span class="sxs-lookup"><span data-stu-id="afc6b-129">Element</span></span>|<span data-ttu-id="afc6b-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afc6b-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="afc6b-131">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="afc6b-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="afc6b-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="afc6b-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="afc6b-133">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="afc6b-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="afc6b-134">Verwenden Sie für jede Assembly ein dependentAssembly-Element.</span><span class="sxs-lookup"><span data-stu-id="afc6b-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="afc6b-135">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="afc6b-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afc6b-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="afc6b-136">Remarks</span></span>  
 <span data-ttu-id="afc6b-137">Wenn Sie eine .NET Framework-Anwendung mit einer Assembly mit starkem Namen erstellen, verwendet die Anwendung zur Laufzeit standardmäßig diese Version der Assembly, selbst wenn eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="afc6b-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="afc6b-138">Sie können die Anwendung jedoch auch so konfigurieren, dass sie mit einer neueren Version der Assembly ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="afc6b-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="afc6b-139">Weitere Informationen dazu, wie die Laufzeit diese Dateien verwendet, um zu bestimmen, welche Assemblyversion verwendet werden soll, finden Sie unter [So sucht die Laufzeit Assemblys](../../../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="afc6b-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="afc6b-140">Sie können mehrere Assemblyversionen umleiten, indem Sie mehrere `bindingRedirect`-Elemente in ein `dependentAssembly`-Element aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="afc6b-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="afc6b-141">Sie können auch von einer neueren Version zu einer früheren Version der Assembly umleiten.</span><span class="sxs-lookup"><span data-stu-id="afc6b-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="afc6b-142">Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afc6b-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="afc6b-143">Dies betrifft die Umleitung von .NET Framework-Assemblys und Assemblys von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="afc6b-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="afc6b-144">Die Berechtigung wird erteilt, indem das <xref:System.Security.Permissions.SecurityPermissionFlag> Flag auf der <xref:System.Security.Permissions.SecurityPermission>gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="afc6b-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="afc6b-145">Weitere Informationen finden Sie unter [Sicherheitsberechtigung für Assemblybindungsumleitung](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="afc6b-145">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="afc6b-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afc6b-146">Example</span></span>  
 <span data-ttu-id="afc6b-147">Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten.</span><span class="sxs-lookup"><span data-stu-id="afc6b-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="afc6b-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="afc6b-148">See also</span></span>

- [<span data-ttu-id="afc6b-149">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="afc6b-149">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="afc6b-150">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="afc6b-150">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="afc6b-151">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="afc6b-151">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
