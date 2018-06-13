---
title: '&lt;AlwaysFlowImpersonationPolicy&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cc704bbf8631936dbbeb3539ea5ed0d8499f378
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752272"
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="fc97d-102">&lt;AlwaysFlowImpersonationPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="fc97d-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="fc97d-103">Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="fc97d-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="fc97d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fc97d-104">\<configuration></span></span>  
<span data-ttu-id="fc97d-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="fc97d-105">\<runtime></span></span>  
<span data-ttu-id="fc97d-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="fc97d-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc97d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc97d-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc97d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc97d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fc97d-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc97d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc97d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc97d-110">Attributes</span></span>  
  
|<span data-ttu-id="fc97d-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="fc97d-111">Attribute</span></span>|<span data-ttu-id="fc97d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc97d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="fc97d-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fc97d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="fc97d-114">Gibt an, ob die Windows-Identität über asynchrone Punkte übergeben.</span><span class="sxs-lookup"><span data-stu-id="fc97d-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fc97d-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="fc97d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="fc97d-116">Wert</span><span class="sxs-lookup"><span data-stu-id="fc97d-116">Value</span></span>|<span data-ttu-id="fc97d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc97d-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="fc97d-118">Die Windows-Identität nicht über asynchrone Punkte übergeben wird, es sei denn, der Identitätswechsel über erfolgt verwaltete Methoden, wie z. B. <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc97d-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="fc97d-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fc97d-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="fc97d-120">Die Windows-Identität fließen immer über asynchrone Punkte, unabhängig davon, wie Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="fc97d-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc97d-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc97d-121">Child Elements</span></span>  
 <span data-ttu-id="fc97d-122">Keine</span><span class="sxs-lookup"><span data-stu-id="fc97d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc97d-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc97d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fc97d-124">Element</span><span class="sxs-lookup"><span data-stu-id="fc97d-124">Element</span></span>|<span data-ttu-id="fc97d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc97d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fc97d-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fc97d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fc97d-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fc97d-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc97d-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc97d-128">Remarks</span></span>  
 <span data-ttu-id="fc97d-129">In der .NET Framework-Versionen 1.0 und 1.1 die Windows-Identität nicht über asynchrone Punkte übergeben.</span><span class="sxs-lookup"><span data-stu-id="fc97d-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="fc97d-130">In .NET Framework, Version 2.0, besteht eine <xref:System.Threading.ExecutionContext> Objekt, das enthält Informationen zu den gerade ausgeführten Thread und übergibt ihn über asynchrone Punkte innerhalb einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="fc97d-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="fc97d-131">Die <xref:System.Security.Principal.WindowsIdentity> auch Datenflüsse im Rahmen der Informationen, die über die asynchrone Punkte fließen bereitgestellten des Identitätswechsels mit verwalteten Methoden wie z. B. <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> und nicht mithilfe anderer Methoden wie z. B. Plattform Aufrufen von systemeigenen Methoden.</span><span class="sxs-lookup"><span data-stu-id="fc97d-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="fc97d-132">Dieses Element wird verwendet, um anzugeben, dass die Windows-Identität über asynchrone Punkte, unabhängig davon, wie des Identitätswechsels fließen.</span><span class="sxs-lookup"><span data-stu-id="fc97d-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="fc97d-133">Sie können dieses Standardverhalten auf zwei andere Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="fc97d-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="fc97d-134">In verwaltetem Code auf eine Threadbasis.</span><span class="sxs-lookup"><span data-stu-id="fc97d-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="fc97d-135">Sie können den Fluss auf eine Threadbasis unterdrücken, indem Sie ändern die <xref:System.Threading.ExecutionContext> und <xref:System.Security.SecurityContext> Einstellungen mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="fc97d-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="fc97d-136">Im Aufruf der nicht verwaltete Hostschnittstelle die common Language Runtime (CLR) geladen.</span><span class="sxs-lookup"><span data-stu-id="fc97d-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="fc97d-137">Wenn eine nicht verwaltete Hostschnittstelle (statt einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag angeben, in dem Aufruf der [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="fc97d-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="fc97d-138">Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie die `flags` -Parameter für [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) auf `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="fc97d-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="fc97d-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fc97d-139">Configuration File</span></span>  
 <span data-ttu-id="fc97d-140">In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc97d-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="fc97d-141">Für eine ASP.NET-Anwendung der Identitätswechsel-Fluss kann in der Datei Aspnet.config-Datei im konfiguriert die \<Ordner "Windows" > \Microsoft.NET\Framework\vx.x.xxxx-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fc97d-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="fc97d-142">ASP.NET standardmäßig deaktiviert den Ablauf Identitätswechsel in aspnet.config-Datei mit den folgenden Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="fc97d-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="fc97d-143">In ASP.NET verwenden Wenn Sie zulassen, den Fluss des Identitätswechsels stattdessen möchten müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="fc97d-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="fc97d-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc97d-144">Example</span></span>  
 <span data-ttu-id="fc97d-145">Das folgende Beispiel zeigt, wie an, dass die Windows-Identität über asynchrone Punkte fließen, selbst wenn der Identitätswechsel Weise als verwaltete Methoden erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="fc97d-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc97d-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc97d-146">See Also</span></span>  
 [<span data-ttu-id="fc97d-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="fc97d-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="fc97d-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="fc97d-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="fc97d-149">\<LegacyImpersonationPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="fc97d-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
