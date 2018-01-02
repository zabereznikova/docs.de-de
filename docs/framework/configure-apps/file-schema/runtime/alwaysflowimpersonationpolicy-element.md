---
title: '&lt;AlwaysFlowImpersonationPolicy&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be1df955f7586848968cb32cd66a4c6889cfffa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="a9c6c-102">&lt;AlwaysFlowImpersonationPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="a9c6c-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="a9c6c-103">Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="a9c6c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a9c6c-104">\<configuration></span></span>  
<span data-ttu-id="a9c6c-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="a9c6c-105">\<runtime></span></span>  
<span data-ttu-id="a9c6c-106">\<AlwaysFlowImpersonationPolicy ></span><span class="sxs-lookup"><span data-stu-id="a9c6c-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c6c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9c6c-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9c6c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a9c6c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a9c6c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9c6c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a9c6c-110">Attributes</span></span>  
  
|<span data-ttu-id="a9c6c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a9c6c-111">Attribute</span></span>|<span data-ttu-id="a9c6c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9c6c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a9c6c-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a9c6c-114">Gibt an, ob die Windows-Identität über asynchrone Punkte übergeben.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a9c6c-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="a9c6c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a9c6c-116">Wert</span><span class="sxs-lookup"><span data-stu-id="a9c6c-116">Value</span></span>|<span data-ttu-id="a9c6c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9c6c-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a9c6c-118">Die Windows-Identität nicht über asynchrone Punkte übergeben wird, es sei denn, der Identitätswechsel über erfolgt verwaltete Methoden, wie z. B. <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="a9c6c-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a9c6c-120">Die Windows-Identität fließen immer über asynchrone Punkte, unabhängig davon, wie Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9c6c-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9c6c-121">Child Elements</span></span>  
 <span data-ttu-id="a9c6c-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a9c6c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9c6c-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9c6c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a9c6c-124">Element</span><span class="sxs-lookup"><span data-stu-id="a9c6c-124">Element</span></span>|<span data-ttu-id="a9c6c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9c6c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a9c6c-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a9c6c-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9c6c-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9c6c-128">Remarks</span></span>  
 <span data-ttu-id="a9c6c-129">In der .NET Framework-Versionen 1.0 und 1.1 die Windows-Identität nicht über asynchrone Punkte übergeben.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="a9c6c-130">In .NET Framework, Version 2.0, besteht eine <xref:System.Threading.ExecutionContext> Objekt, das enthält Informationen zu den gerade ausgeführten Thread und übergibt ihn über asynchrone Punkte innerhalb einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="a9c6c-131">Die <xref:System.Security.Principal.WindowsIdentity> auch Datenflüsse im Rahmen der Informationen, die über die asynchrone Punkte fließen bereitgestellten des Identitätswechsels mit verwalteten Methoden wie z. B. <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> und nicht mithilfe anderer Methoden wie z. B. Plattform Aufrufen von systemeigenen Methoden.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="a9c6c-132">Dieses Element wird verwendet, um anzugeben, dass die Windows-Identität über asynchrone Punkte, unabhängig davon, wie des Identitätswechsels fließen.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="a9c6c-133">Sie können dieses Standardverhalten auf zwei andere Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="a9c6c-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="a9c6c-134">In verwaltetem Code auf eine Threadbasis.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="a9c6c-135">Sie können den Fluss auf eine Threadbasis unterdrücken, indem Sie ändern die <xref:System.Threading.ExecutionContext> und <xref:System.Security.SecurityContext> Einstellungen mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="a9c6c-136">Im Aufruf der nicht verwaltete Hostschnittstelle die common Language Runtime (CLR) geladen.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="a9c6c-137">Wenn eine nicht verwaltete Hostschnittstelle (statt einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag angeben, in dem Aufruf der [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="a9c6c-138">Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie die `flags` -Parameter für [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) auf `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a9c6c-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a9c6c-139">Configuration File</span></span>  
 <span data-ttu-id="a9c6c-140">In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="a9c6c-141">Für eine ASP.NET-Anwendung der Identitätswechsel-Fluss kann in der Datei Aspnet.config-Datei im konfiguriert die \<Ordner "Windows" > \Microsoft.NET\Framework\vx.x.xxxx-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="a9c6c-142">ASP.NET standardmäßig deaktiviert den Ablauf Identitätswechsel in aspnet.config-Datei mit den folgenden Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="a9c6c-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="a9c6c-143">In ASP.NET verwenden Wenn Sie zulassen, den Fluss des Identitätswechsels stattdessen möchten müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="a9c6c-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="a9c6c-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9c6c-144">Example</span></span>  
 <span data-ttu-id="a9c6c-145">Das folgende Beispiel zeigt, wie an, dass die Windows-Identität über asynchrone Punkte fließen, selbst wenn der Identitätswechsel Weise als verwaltete Methoden erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9c6c-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9c6c-146">See Also</span></span>  
 [<span data-ttu-id="a9c6c-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a9c6c-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a9c6c-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a9c6c-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a9c6c-149">\<LegacyImpersonationPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="a9c6c-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
