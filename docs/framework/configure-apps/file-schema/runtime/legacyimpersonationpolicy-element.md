---
title: <legacyImpersonationPolicy>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: 18a027bc09f2400a10a06efdc4c5355686bcb56d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116540"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="e1fc2-102">\<legacyidentitäts-> Element</span><span class="sxs-lookup"><span data-stu-id="e1fc2-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="e1fc2-103">Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="e1fc2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1fc2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e1fc2-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="e1fc2-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e1fc2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<legacyidentität** ></span><span class="sxs-lookup"><span data-stu-id="e1fc2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fc2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1fc2-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1fc2-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1fc2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e1fc2-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1fc2-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1fc2-110">Attributes</span></span>  
  
|<span data-ttu-id="e1fc2-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e1fc2-111">Attribute</span></span>|<span data-ttu-id="e1fc2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1fc2-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e1fc2-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e1fc2-114">Gibt an, dass der <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte fließt, unabhängig von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e1fc2-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="e1fc2-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e1fc2-116">Wert</span><span class="sxs-lookup"><span data-stu-id="e1fc2-116">Value</span></span>|<span data-ttu-id="e1fc2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1fc2-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e1fc2-118"><xref:System.Security.Principal.WindowsIdentity> in Abhängigkeit von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen für den aktuellen Thread über asynchrone Punkte hinweg.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="e1fc2-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="e1fc2-120"><xref:System.Security.Principal.WindowsIdentity> erfolgt nicht über asynchrone Punkte, unabhängig von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1fc2-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1fc2-121">Child Elements</span></span>  
 <span data-ttu-id="e1fc2-122">Keine</span><span class="sxs-lookup"><span data-stu-id="e1fc2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1fc2-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1fc2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e1fc2-124">Element</span><span class="sxs-lookup"><span data-stu-id="e1fc2-124">Element</span></span>|<span data-ttu-id="e1fc2-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1fc2-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e1fc2-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e1fc2-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1fc2-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1fc2-128">Remarks</span></span>  
 <span data-ttu-id="e1fc2-129">In den .NET Framework Versionen 1,0 und 1,1 fließt der <xref:System.Security.Principal.WindowsIdentity> nicht über benutzerdefinierte asynchrone Punkte hinweg.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="e1fc2-130">Beginnend mit der .NET Framework Version 2,0 gibt es ein <xref:System.Threading.ExecutionContext> Objekt, das Informationen über den aktuell ausgeführten Thread enthält und über asynchrone Punkte innerhalb einer Anwendungsdomäne fließt.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="e1fc2-131">Der <xref:System.Security.Principal.WindowsIdentity> ist in diesem Ausführungs Kontext enthalten und verläuft daher auch über die asynchronen Punkte. Dies bedeutet, dass, wenn ein Identitätswechsel Kontext vorhanden ist, auch ein Flow ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="e1fc2-132">Beginnend mit dem .NET Framework 2,0 können Sie das `<legacyImpersonationPolicy>`-Element verwenden, um anzugeben, dass <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte fließt.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1fc2-133">Der Common Language Runtime (CLR) kennt Identitätswechsel Vorgänge, die nur mit verwaltetem Code ausgeführt werden, nicht den Identitätswechsel außerhalb von verwaltetem Code, wie z. b. durch Platt Form Aufrufe zu nicht verwaltetem Code oder durch direkte Aufrufe von Win32-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="e1fc2-134">Nur verwaltete <xref:System.Security.Principal.WindowsIdentity> Objekte können über asynchrone Punkte hinweg fließen, es sei denn, das `alwaysFlowImpersonationPolicy`-Element wurde auf true (`<alwaysFlowImpersonationPolicy enabled="true"/>`) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="e1fc2-135">Wenn das `alwaysFlowImpersonationPolicy`-Element auf true festgelegt wird, wird angegeben, dass die Windows-Identität immer asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="e1fc2-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="e1fc2-136">Weitere Informationen zum Übertragen von nicht verwaltetem Identitätswechsel über asynchrone Punkte hinweg finden Sie unter [\<alwaysFlowImpersonationPolicy >-Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="e1fc2-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="e1fc2-137">Sie können dieses Standardverhalten auf zwei verschiedene Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="e1fc2-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="e1fc2-138">In verwaltetem Code auf Thread Basis.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="e1fc2-139">Sie können den Flow Thread bezogen unterdrücken, indem Sie die <xref:System.Threading.ExecutionContext>-und <xref:System.Security.SecurityContext> Einstellungen mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>-, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>-oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>-Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="e1fc2-140">Im aufzurufenden Befehl an die nicht verwaltete Hostingschnittstelle zum Laden der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e1fc2-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="e1fc2-141">Wenn eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag im Aufrufen der [CorBindToRuntimeEx-Funktions](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion angeben.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="e1fc2-142">Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie den `flags`-Parameter für die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP_LEGACY_IMPERSONATION fest.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="e1fc2-143">Weitere Informationen finden Sie unter [\<alwaysFlowImpersonationPolicy >-Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="e1fc2-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e1fc2-144">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e1fc2-144">Configuration File</span></span>  
 <span data-ttu-id="e1fc2-145">In einer .NET Framework Anwendung kann dieses Element nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="e1fc2-146">Bei einer ASP.NET-Anwendung kann der Identitätswechsel in der ASPNET. config-Datei konfiguriert werden, die sich im \<Windows-Ordner > \Microsoft.NET\Framework\vx.x.xxxx-Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="e1fc2-147">ASP.net deaktiviert den Identitätswechsel in der Datei Aspnet. config standardmäßig mithilfe der folgenden Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="e1fc2-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="e1fc2-148">Wenn Sie in ASP.NET den Fluss des Identitäts Wechsels zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e1fc2-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="e1fc2-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1fc2-149">Example</span></span>  
 <span data-ttu-id="e1fc2-150">Im folgenden Beispiel wird gezeigt, wie das Legacy Verhalten angegeben wird, das die Windows-Identität nicht über asynchrone Punkte hinweg fließt.</span><span class="sxs-lookup"><span data-stu-id="e1fc2-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1fc2-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1fc2-151">See also</span></span>

- [<span data-ttu-id="e1fc2-152">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e1fc2-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e1fc2-153">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e1fc2-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e1fc2-154">\<alwaysFlowImpersonationPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="e1fc2-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
