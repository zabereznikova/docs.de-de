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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154103"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="02e45-102">\<legacyImpersonationPolicy>-Element</span><span class="sxs-lookup"><span data-stu-id="02e45-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="02e45-103">Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="02e45-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="02e45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02e45-104">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02e45-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02e45-105">Attributes and Elements</span></span>  
 <span data-ttu-id="02e45-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02e45-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02e45-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="02e45-107">Attributes</span></span>  
  
|<span data-ttu-id="02e45-108">attribute</span><span class="sxs-lookup"><span data-stu-id="02e45-108">Attribute</span></span>|<span data-ttu-id="02e45-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02e45-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="02e45-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="02e45-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="02e45-111">Gibt an, dass der <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte fließt, unabhängig von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="02e45-111">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="02e45-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="02e45-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="02e45-113">Wert</span><span class="sxs-lookup"><span data-stu-id="02e45-113">Value</span></span>|<span data-ttu-id="02e45-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02e45-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="02e45-115"><xref:System.Security.Principal.WindowsIdentity>verläuft in Abhängigkeit von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen für den aktuellen Thread über asynchrone Punkte hinweg.</span><span class="sxs-lookup"><span data-stu-id="02e45-115"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="02e45-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="02e45-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="02e45-117"><xref:System.Security.Principal.WindowsIdentity>fließt nicht über asynchrone Punkte hinweg, unabhängig von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="02e45-117"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02e45-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02e45-118">Child Elements</span></span>  
 <span data-ttu-id="02e45-119">Keine</span><span class="sxs-lookup"><span data-stu-id="02e45-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02e45-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02e45-120">Parent Elements</span></span>  
  
|<span data-ttu-id="02e45-121">Element</span><span class="sxs-lookup"><span data-stu-id="02e45-121">Element</span></span>|<span data-ttu-id="02e45-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02e45-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02e45-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="02e45-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="02e45-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="02e45-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02e45-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="02e45-125">Remarks</span></span>  
 <span data-ttu-id="02e45-126">In den .NET Framework Versionen 1,0 und 1,1 fließt der <xref:System.Security.Principal.WindowsIdentity> nicht über benutzerdefinierte asynchrone Punkte.</span><span class="sxs-lookup"><span data-stu-id="02e45-126">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="02e45-127">Beginnend mit der .NET Framework Version 2,0 gibt es ein <xref:System.Threading.ExecutionContext> Objekt, das Informationen über den aktuell ausgeführten Thread enthält und über asynchrone Punkte innerhalb einer Anwendungsdomäne fließt.</span><span class="sxs-lookup"><span data-stu-id="02e45-127">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="02e45-128">Der <xref:System.Security.Principal.WindowsIdentity> ist in diesem Ausführungs Kontext enthalten und verläuft daher auch über die asynchronen Punkte. Dies bedeutet, dass, wenn ein Identitätswechsel Kontext vorhanden ist, auch der Fluss erfolgt.</span><span class="sxs-lookup"><span data-stu-id="02e45-128">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="02e45-129">Beginnend mit dem .NET Framework 2,0 können Sie das-Element verwenden, `<legacyImpersonationPolicy>` um anzugeben, dass <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte fließt.</span><span class="sxs-lookup"><span data-stu-id="02e45-129">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02e45-130">Der Common Language Runtime (CLR) kennt Identitätswechsel Vorgänge, die nur mit verwaltetem Code ausgeführt werden, nicht den Identitätswechsel außerhalb von verwaltetem Code, wie z. b. durch Platt Form Aufrufe zu nicht verwaltetem Code oder durch direkte Aufrufe von Win32-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="02e45-130">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="02e45-131">Nur verwaltete <xref:System.Security.Principal.WindowsIdentity> Objekte können über asynchrone Punkte hinweg fließen, es sei denn, das `alwaysFlowImpersonationPolicy` Element wurde auf true () festgelegt `<alwaysFlowImpersonationPolicy enabled="true"/>` .</span><span class="sxs-lookup"><span data-stu-id="02e45-131">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="02e45-132">Das Festlegen des- `alwaysFlowImpersonationPolicy` Elements auf true gibt an, dass die Windows-Identität immer über asynchrone Punkte hinweg verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="02e45-132">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="02e45-133">Weitere Informationen zum Übertragen von nicht verwaltetem Identitätswechsel über asynchrone Punkte hinweg finden Sie unter [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="02e45-133">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="02e45-134">Sie können dieses Standardverhalten auf zwei verschiedene Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="02e45-134">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="02e45-135">In verwaltetem Code auf Thread Basis.</span><span class="sxs-lookup"><span data-stu-id="02e45-135">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="02e45-136">Sie können den Flow auf Thread Basis unterdrücken, indem Sie die <xref:System.Threading.ExecutionContext> -Einstellung und die- <xref:System.Security.SecurityContext> Einstellung mithilfe der- <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> ,-oder-Methode ändern <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="02e45-136">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="02e45-137">Im aufzurufenden Befehl an die nicht verwaltete Hostingschnittstelle zum Laden der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="02e45-137">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="02e45-138">Wenn eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag im Aufrufen der [CorBindToRuntimeEx-Funktions](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion angeben.</span><span class="sxs-lookup"><span data-stu-id="02e45-138">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="02e45-139">Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie den- `flags` Parameter für die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP_LEGACY_IMPERSONATION fest.</span><span class="sxs-lookup"><span data-stu-id="02e45-139">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="02e45-140">Weitere Informationen finden Sie unter dem- [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="02e45-140">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="02e45-141">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="02e45-141">Configuration File</span></span>  
 <span data-ttu-id="02e45-142">In einer .NET Framework Anwendung kann dieses Element nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02e45-142">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="02e45-143">Bei einer ASP.NET-Anwendung kann der Identitätswechsel in der ASPNET. config-Datei konfiguriert werden, die im \<Windows Folder> Verzeichnis \Microsoft.NET\Framework\vx.x.xxxx enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="02e45-143">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="02e45-144">ASP.net deaktiviert den Identitätswechsel in der Datei Aspnet. config standardmäßig mithilfe der folgenden Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="02e45-144">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="02e45-145">Wenn Sie in ASP.NET den Fluss des Identitäts Wechsels zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="02e45-145">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="02e45-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02e45-146">Example</span></span>  
 <span data-ttu-id="02e45-147">Im folgenden Beispiel wird gezeigt, wie das Legacy Verhalten angegeben wird, das die Windows-Identität nicht über asynchrone Punkte hinweg fließt.</span><span class="sxs-lookup"><span data-stu-id="02e45-147">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02e45-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02e45-148">See also</span></span>

- [<span data-ttu-id="02e45-149">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="02e45-149">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="02e45-150">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="02e45-150">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="02e45-151">\<alwaysFlowImpersonationPolicy>Gewisses</span><span class="sxs-lookup"><span data-stu-id="02e45-151">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
