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
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154103"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="56bc6-102">\<legacyImpersonationPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="56bc6-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="56bc6-103">Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="56bc6-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="56bc6-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="56bc6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="56bc6-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="56bc6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="56bc6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span><span class="sxs-lookup"><span data-stu-id="56bc6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56bc6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="56bc6-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56bc6-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56bc6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="56bc6-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56bc6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56bc6-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="56bc6-110">Attributes</span></span>  
  
|<span data-ttu-id="56bc6-111">attribute</span><span class="sxs-lookup"><span data-stu-id="56bc6-111">Attribute</span></span>|<span data-ttu-id="56bc6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56bc6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="56bc6-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="56bc6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="56bc6-114">Gibt an, <xref:System.Security.Principal.WindowsIdentity> dass der nicht über asynchrone <xref:System.Threading.ExecutionContext> Punkte fließt, unabhängig von den Flusseinstellungen im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="56bc6-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="56bc6-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="56bc6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="56bc6-116">value</span><span class="sxs-lookup"><span data-stu-id="56bc6-116">Value</span></span>|<span data-ttu-id="56bc6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56bc6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="56bc6-118"><xref:System.Security.Principal.WindowsIdentity>fließt über asynchrone Punkte, abhängig von den <xref:System.Threading.ExecutionContext> Flusseinstellungen für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="56bc6-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="56bc6-119">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="56bc6-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="56bc6-120"><xref:System.Security.Principal.WindowsIdentity>fließt nicht über asynchrone Punkte, <xref:System.Threading.ExecutionContext> unabhängig von den Flusseinstellungen im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="56bc6-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56bc6-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56bc6-121">Child Elements</span></span>  
 <span data-ttu-id="56bc6-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="56bc6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56bc6-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56bc6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="56bc6-124">Element</span><span class="sxs-lookup"><span data-stu-id="56bc6-124">Element</span></span>|<span data-ttu-id="56bc6-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56bc6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="56bc6-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="56bc6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="56bc6-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="56bc6-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56bc6-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="56bc6-128">Remarks</span></span>  
 <span data-ttu-id="56bc6-129">In den .NET Framework-Versionen 1.0 <xref:System.Security.Principal.WindowsIdentity> und 1.1 fließt der nicht über benutzerdefinierte asynchrone Punkte.</span><span class="sxs-lookup"><span data-stu-id="56bc6-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="56bc6-130">Ab .NET Framework Version 2.0 gibt <xref:System.Threading.ExecutionContext> es ein Objekt, das Informationen über den aktuell ausgeführten Thread enthält und über asynchrone Punkte innerhalb einer Anwendungsdomäne fließt.</span><span class="sxs-lookup"><span data-stu-id="56bc6-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="56bc6-131">Der <xref:System.Security.Principal.WindowsIdentity> ist in diesem Ausführungskontext enthalten und fließt daher auch über die asynchronen Punkte, was bedeutet, dass, wenn ein Identitätswechselkontext vorhanden ist, er auch fließt.</span><span class="sxs-lookup"><span data-stu-id="56bc6-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="56bc6-132">Ab .NET Framework 2.0 können Sie `<legacyImpersonationPolicy>` das Element <xref:System.Security.Principal.WindowsIdentity> verwenden, um anzugeben, dass es nicht über asynchrone Punkte fließt.</span><span class="sxs-lookup"><span data-stu-id="56bc6-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56bc6-133">Die Common Language Runtime (CLR) ist sich der Identitätswechselvorgänge bewusst, die nur mit verwaltetem Code ausgeführt werden, und nicht von Identitätswechsel, die außerhalb des verwalteten Codes ausgeführt werden, z. B. durch Plattformaufruf an nicht verwalteten Code oder durch direkte Aufrufe von Win32-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="56bc6-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="56bc6-134">Nur <xref:System.Security.Principal.WindowsIdentity> verwaltete Objekte können über asynchrone Punkte fließen, es sei denn, das `alwaysFlowImpersonationPolicy` Element wurde auf true (`<alwaysFlowImpersonationPolicy enabled="true"/>`) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56bc6-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="56bc6-135">Wenn `alwaysFlowImpersonationPolicy` Sie das Element auf true festlegen, wird angegeben, dass die Windows-Identität immer über asynchrone Punkte fließt, unabhängig davon, wie Identitätswechsel ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="56bc6-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="56bc6-136">Weitere Informationen zum Fließen von nicht verwaltetem Identitätswechsel über asynchrone Punkte finden Sie unter [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="56bc6-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="56bc6-137">Sie können dieses Standardverhalten auf zwei weitere Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="56bc6-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="56bc6-138">In verwaltetem Code pro Thread.</span><span class="sxs-lookup"><span data-stu-id="56bc6-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="56bc6-139">Sie können den Fluss pro Thread unterdrücken, <xref:System.Threading.ExecutionContext> indem <xref:System.Security.SecurityContext> Sie die <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> und <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> die Einstellungen mithilfe der , oder Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="56bc6-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="56bc6-140">Beim Aufruf der nicht verwalteten Hostingschnittstelle, um die Common Language Runtime (CLR) zu laden.</span><span class="sxs-lookup"><span data-stu-id="56bc6-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="56bc6-141">Wenn zum Laden der CLR eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) verwendet wird, können Sie im Aufruf der [Funktion CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) ein spezielles Flag angeben.</span><span class="sxs-lookup"><span data-stu-id="56bc6-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="56bc6-142">Um den Kompatibilitätsmodus für den gesamten `flags` Prozess zu aktivieren, legen Sie den Parameter für [die CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="56bc6-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="56bc6-143">Weitere Informationen finden Sie in der [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="56bc6-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="56bc6-144">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="56bc6-144">Configuration File</span></span>  
 <span data-ttu-id="56bc6-145">In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56bc6-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="56bc6-146">Bei einer ASP.NET Anwendung kann der Identitätswechselfluss in der Datei aspnet.config konfiguriert werden, die \<im Verzeichnis "Windows-Ordner">-Verzeichnis "Microsoft.NET-Framework" und "vx.x.xxxx" gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="56bc6-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="56bc6-147">ASP.NET deaktiviert standardmäßig den Identitätswechselfluss in der Datei aspnet.config mithilfe der folgenden Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="56bc6-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="56bc6-148">Wenn Sie in ASP.NET stattdessen den Fluss des Identitätswechsels zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="56bc6-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="56bc6-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56bc6-149">Example</span></span>  
 <span data-ttu-id="56bc6-150">Das folgende Beispiel zeigt, wie Sie das Legacyverhalten angeben, das die Windows-Identität nicht über asynchrone Punkte hinweg durchläuft.</span><span class="sxs-lookup"><span data-stu-id="56bc6-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56bc6-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56bc6-151">See also</span></span>

- [<span data-ttu-id="56bc6-152">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="56bc6-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="56bc6-153">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="56bc6-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="56bc6-154">\<alwaysFlowImpersonationPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="56bc6-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
