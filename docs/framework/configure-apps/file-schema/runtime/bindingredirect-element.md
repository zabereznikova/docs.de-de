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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154295"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="ff718-102">\<bindingRedirect>-Element</span><span class="sxs-lookup"><span data-stu-id="ff718-102">\<bindingRedirect> Element</span></span>
<span data-ttu-id="ff718-103">Leitet eine Assemblyversion in eine andere um.</span><span class="sxs-lookup"><span data-stu-id="ff718-103">Redirects one assembly version to another.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**  
  
## <a name="syntax"></a><span data-ttu-id="ff718-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff718-104">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff718-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ff718-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ff718-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff718-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff718-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="ff718-107">Attributes</span></span>  
  
|<span data-ttu-id="ff718-108">attribute</span><span class="sxs-lookup"><span data-stu-id="ff718-108">Attribute</span></span>|<span data-ttu-id="ff718-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff718-109">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="ff718-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ff718-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="ff718-111">Gibt die Assemblyversion an, die ursprünglich angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="ff718-111">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="ff718-112">Das Format einer Assemblyversionsnummer ist *Hauptversion. neben Version. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="ff718-112">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="ff718-113">Gültige Werte für jeden Abschnitt dieser Versionsnummer sind 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="ff718-113">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="ff718-114">Sie können auch einen Bereich an Versionsnummern angeben, und zwar im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="ff718-114">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="ff718-115">*n. n. n. n-n. n. n. n*</span><span class="sxs-lookup"><span data-stu-id="ff718-115">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="ff718-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ff718-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ff718-117">Gibt die Version der Assembly an, die anstelle der ursprünglich angeforderten Version im folgenden Format verwendet werden soll: *n. n. n. n*</span><span class="sxs-lookup"><span data-stu-id="ff718-117">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="ff718-118">Dieser Wert kann eine frühere Version als `oldVersion` angeben.</span><span class="sxs-lookup"><span data-stu-id="ff718-118">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff718-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff718-119">Child Elements</span></span>  
  
|<span data-ttu-id="ff718-120">Element</span><span class="sxs-lookup"><span data-stu-id="ff718-120">Element</span></span>|<span data-ttu-id="ff718-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff718-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff718-122">Keine</span><span class="sxs-lookup"><span data-stu-id="ff718-122">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="ff718-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff718-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ff718-124">Element</span><span class="sxs-lookup"><span data-stu-id="ff718-124">Element</span></span>|<span data-ttu-id="ff718-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff718-125">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="ff718-126">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="ff718-126">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="ff718-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ff718-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="ff718-128">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="ff718-128">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="ff718-129">Verwenden Sie für jede Assembly ein dependentAssembly-Element.</span><span class="sxs-lookup"><span data-stu-id="ff718-129">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="ff718-130">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ff718-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff718-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ff718-131">Remarks</span></span>  
 <span data-ttu-id="ff718-132">Wenn Sie eine .NET Framework-Anwendung mit einer Assembly mit starkem Namen erstellen, verwendet die Anwendung zur Laufzeit standardmäßig diese Version der Assembly, selbst wenn eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ff718-132">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="ff718-133">Sie können die Anwendung jedoch auch so konfigurieren, dass sie mit einer neueren Version der Assembly ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff718-133">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="ff718-134">Ausführliche Informationen dazu, wie die Common Language Runtime diese Dateien verwendet, um zu bestimmen, welche Assemblyversion verwendet werden soll, finden Sie unter so sucht Common Language [Runtime](../../../deployment/how-the-runtime-locates-assemblies.md)</span><span class="sxs-lookup"><span data-stu-id="ff718-134">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="ff718-135">Sie können mehrere Assemblyversionen umleiten, indem Sie mehrere `bindingRedirect`-Elemente in ein `dependentAssembly`-Element aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="ff718-135">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="ff718-136">Sie können auch von einer neueren Version zu einer früheren Version der Assembly umleiten.</span><span class="sxs-lookup"><span data-stu-id="ff718-136">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="ff718-137">Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ff718-137">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="ff718-138">Dies betrifft die Umleitung von .NET Framework-Assemblys und Assemblys von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="ff718-138">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="ff718-139">Die Berechtigung wird erteilt, indem das-Flag auf festgelegt wird <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="ff718-139">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="ff718-140">Weitere Informationen finden Sie unter [Sicherheits Berechtigung für die assemblybindungsumleitung](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="ff718-140">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff718-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff718-141">Example</span></span>  
 <span data-ttu-id="ff718-142">Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten.</span><span class="sxs-lookup"><span data-stu-id="ff718-142">The following example shows how to redirect one assembly version to another.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff718-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff718-143">See also</span></span>

- [<span data-ttu-id="ff718-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ff718-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ff718-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ff718-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ff718-146">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="ff718-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
