---
title: '&lt;legacyImpersonationPolicy&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196aaa35561cba7925bcd005474cccb393494250
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699883"
---
# <a name="ltlegacyimpersonationpolicygt-element"></a><span data-ttu-id="33884-102">&lt;legacyImpersonationPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="33884-102">&lt;legacyImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="33884-103">Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="33884-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="33884-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="33884-104">\<configuration></span></span>  
<span data-ttu-id="33884-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="33884-105">\<runtime></span></span>  
<span data-ttu-id="33884-106">\<legacyImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="33884-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33884-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="33884-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33884-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="33884-108">Attributes and Elements</span></span>  
 <span data-ttu-id="33884-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="33884-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33884-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="33884-110">Attributes</span></span>  
  
|<span data-ttu-id="33884-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="33884-111">Attribute</span></span>|<span data-ttu-id="33884-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33884-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="33884-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="33884-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="33884-114">Gibt an, dass die <xref:System.Security.Principal.WindowsIdentity> fließen nicht über asynchrone Punkte verläuft, unabhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="33884-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="33884-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="33884-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="33884-116">Wert</span><span class="sxs-lookup"><span data-stu-id="33884-116">Value</span></span>|<span data-ttu-id="33884-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33884-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="33884-118"><xref:System.Security.Principal.WindowsIdentity> Flows über asynchrone Punkte, die abhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="33884-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="33884-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="33884-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="33884-120"><xref:System.Security.Principal.WindowsIdentity> fließen nicht über asynchrone Punkte verläuft, unabhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="33884-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33884-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33884-121">Child Elements</span></span>  
 <span data-ttu-id="33884-122">Keine</span><span class="sxs-lookup"><span data-stu-id="33884-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33884-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33884-123">Parent Elements</span></span>  
  
|<span data-ttu-id="33884-124">Element</span><span class="sxs-lookup"><span data-stu-id="33884-124">Element</span></span>|<span data-ttu-id="33884-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33884-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="33884-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="33884-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="33884-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="33884-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33884-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33884-128">Remarks</span></span>  
 <span data-ttu-id="33884-129">In den .NET Framework-Versionen 1.0 und 1.1 die <xref:System.Security.Principal.WindowsIdentity> nicht über benutzerdefinierte asynchrone Punkte übergeben.</span><span class="sxs-lookup"><span data-stu-id="33884-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="33884-130">Ab .NET Framework, Version 2.0, es ist ein <xref:System.Threading.ExecutionContext> -Objekt, das Informationen zu den aktuell ausgeführten Thread und enthält, die über asynchrone Punkte innerhalb einer Anwendungsdomäne übergeben.</span><span class="sxs-lookup"><span data-stu-id="33884-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="33884-131">Die <xref:System.Security.Principal.WindowsIdentity> in diesem Ausführungskontext enthalten ist, und daher auch über die asynchrone Punkte verläuft, was bedeutet, dass wenn der Kontext eines Identitätswechsels vorhanden ist, es auch fließt.</span><span class="sxs-lookup"><span data-stu-id="33884-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="33884-132">Ab .NET Framework 2.0, können Sie die `<legacyImpersonationPolicy>` Element an, dass <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte übergeben.</span><span class="sxs-lookup"><span data-stu-id="33884-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33884-133">Die common Language Runtime (CLR) beachtet des Identitätswechsels, die für das Aufrufen von Vorgängen, die ausgeführt wird, verwenden nur verwalteter Code, nicht des Identitätswechsels, die außerhalb von verwaltetem Code, z. B. über Plattform ausgeführt, von nicht verwaltetem Code oder durch direkte Aufrufe für Win32-Funktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="33884-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="33884-134">Nur verwaltete <xref:System.Security.Principal.WindowsIdentity> -Objekte können über asynchrone Punkte übergeben, es sei denn, die `alwaysFlowImpersonationPolicy` Elements wurde festgelegt auf "true" (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="33884-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="33884-135">Festlegen der `alwaysFlowImpersonationPolicy` Element auf "true" gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="33884-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="33884-136">Weitere Informationen zur Übergabe von nicht verwaltetem Identitätswechsel über asynchrone Punkte, finden Sie unter [ \<AlwaysFlowImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="33884-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="33884-137">Sie können dieses Standardverhalten auf zwei weitere Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="33884-137">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="33884-138">In verwaltetem Code auf einer pro-Thread-Basis.</span><span class="sxs-lookup"><span data-stu-id="33884-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="33884-139">Sie können den Fluss auf einer pro-Thread-Basis unterdrücken, indem Sie ändern die <xref:System.Threading.ExecutionContext> und <xref:System.Security.SecurityContext> Einstellungen mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="33884-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="33884-140">Im Aufruf der nicht verwaltete Hostschnittstelle die common Language Runtime (CLR) geladen.</span><span class="sxs-lookup"><span data-stu-id="33884-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="33884-141">Wenn eine nicht verwaltete Hostschnittstelle (anstatt eine einfache verwaltete ausführbare Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag angeben, in dem Aufruf der [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="33884-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="33884-142">Legen Sie zum Aktivieren des Kompatibilitätsmodus für den gesamten Prozess der `flags` -Parameter für [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP_LEGACY_IMPERSONATION fest.</span><span class="sxs-lookup"><span data-stu-id="33884-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="33884-143">Weitere Informationen finden Sie unter den [ \<AlwaysFlowImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="33884-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="33884-144">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="33884-144">Configuration File</span></span>  
 <span data-ttu-id="33884-145">In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33884-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="33884-146">Für eine ASP.NET-Anwendung kann der Identitätswechsel-Flow in der Datei "aspnet.config" finden Sie unter konfiguriert werden die \<Windows-Ordner > \Microsoft.NET\Framework\vx.x.xxxx-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="33884-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="33884-147">ASP.NET standardmäßig deaktiviert über die folgenden Konfigurationseinstellungen den Identitätswechsel-Flow in der Datei aspnet.config hinzu:</span><span class="sxs-lookup"><span data-stu-id="33884-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="33884-148">In ASP.NET, wenn Sie zulassen, den Fluss des Identitätswechsels stattdessen möchten müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="33884-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="33884-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33884-149">Example</span></span>  
 <span data-ttu-id="33884-150">Das folgende Beispiel zeigt, wie Sie das Legacyverhalten angeben, das nicht die Windows-Identität über asynchrone Punkte übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="33884-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33884-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33884-151">See also</span></span>
- [<span data-ttu-id="33884-152">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="33884-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="33884-153">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="33884-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="33884-154">\<AlwaysFlowImpersonationPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="33884-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
