---
title: <alwaysFlowImpersonationPolicy>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154482"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="c166a-102">\<alwaysFlowImpersonationPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="c166a-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="c166a-103">Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c166a-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="c166a-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c166a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c166a-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="c166a-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c166a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span><span class="sxs-lookup"><span data-stu-id="c166a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="c166a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c166a-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c166a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c166a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c166a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c166a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c166a-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="c166a-110">Attributes</span></span>  
  
|<span data-ttu-id="c166a-111">attribute</span><span class="sxs-lookup"><span data-stu-id="c166a-111">Attribute</span></span>|<span data-ttu-id="c166a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c166a-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c166a-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c166a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c166a-114">Gibt an, ob die Windows-Identität über asynchrone Punkte fließt.</span><span class="sxs-lookup"><span data-stu-id="c166a-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c166a-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="c166a-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c166a-116">value</span><span class="sxs-lookup"><span data-stu-id="c166a-116">Value</span></span>|<span data-ttu-id="c166a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c166a-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c166a-118">Die Windows-Identität fließt nicht über asynchrone Punkte, es sei denn, der Identitätswechsel wird über verwaltete Methoden wie <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c166a-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="c166a-119">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="c166a-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c166a-120">Die Windows-Identität fließt immer über asynchrone Punkte, unabhängig davon, wie Identitätswechsel ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c166a-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c166a-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c166a-121">Child Elements</span></span>  
 <span data-ttu-id="c166a-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="c166a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c166a-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c166a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c166a-124">Element</span><span class="sxs-lookup"><span data-stu-id="c166a-124">Element</span></span>|<span data-ttu-id="c166a-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c166a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c166a-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c166a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c166a-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c166a-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c166a-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c166a-128">Remarks</span></span>  
 <span data-ttu-id="c166a-129">In den .NET Framework-Versionen 1.0 und 1.1 fließt die Windows-Identität nicht über asynchrone Punkte.</span><span class="sxs-lookup"><span data-stu-id="c166a-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="c166a-130">In .NET Framework Version 2.0 <xref:System.Threading.ExecutionContext> gibt es ein Objekt, das Informationen über den aktuell ausgeführten Thread enthält und es über asynchrone Punkte innerhalb einer Anwendungsdomäne überträgt.</span><span class="sxs-lookup"><span data-stu-id="c166a-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="c166a-131">Der <xref:System.Security.Principal.WindowsIdentity> fließt auch als Teil der Informationen, die über die asynchronen Punkte fließen, <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> vorausgesetzt, der Identitätswechsel wurde mit verwalteten Methoden erreicht, z. B. und nicht mit anderen Mitteln, wie z. B. Plattformaufruf auf systemeigenen Methoden.</span><span class="sxs-lookup"><span data-stu-id="c166a-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="c166a-132">Dieses Element wird verwendet, um anzugeben, dass die Windows-Identität über asynchrone Punkte fließt, unabhängig davon, wie der Identitätswechsel erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="c166a-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="c166a-133">Sie können dieses Standardverhalten auf zwei weitere Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="c166a-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="c166a-134">In verwaltetem Code pro Thread.</span><span class="sxs-lookup"><span data-stu-id="c166a-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="c166a-135">Sie können den Fluss pro Thread unterdrücken, <xref:System.Threading.ExecutionContext> indem <xref:System.Security.SecurityContext> Sie die <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>und <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> die Einstellungen mithilfe der , oder Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="c166a-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="c166a-136">Beim Aufruf der nicht verwalteten Hostingschnittstelle, um die Common Language Runtime (CLR) zu laden.</span><span class="sxs-lookup"><span data-stu-id="c166a-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="c166a-137">Wenn zum Laden der CLR eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) verwendet wird, können Sie im Aufruf der [Funktion CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) ein spezielles Flag angeben.</span><span class="sxs-lookup"><span data-stu-id="c166a-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="c166a-138">Um den Kompatibilitätsmodus für den gesamten `flags` Prozess zu aktivieren, legen `STARTUP_ALWAYSFLOW_IMPERSONATION`Sie den Parameter für [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf fest.</span><span class="sxs-lookup"><span data-stu-id="c166a-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c166a-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c166a-139">Configuration File</span></span>  
 <span data-ttu-id="c166a-140">In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c166a-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="c166a-141">Bei einer ASP.NET Anwendung kann der Identitätswechselfluss in der Datei aspnet.config konfiguriert werden, die \<im Verzeichnis "Windows-Ordner">-Verzeichnis "Microsoft.NET-Framework" und "vx.x.xxxx" gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="c166a-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="c166a-142">ASP.NET deaktiviert standardmäßig den Identitätswechselfluss in der Datei aspnet.config mithilfe der folgenden Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="c166a-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c166a-143">Wenn Sie in ASP.NET stattdessen den Fluss des Identitätswechsels zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="c166a-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="c166a-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c166a-144">Example</span></span>  
 <span data-ttu-id="c166a-145">Das folgende Beispiel zeigt, wie Sie angeben, dass die Windows-Identität über asynchrone Punkte fließt, auch wenn der Identitätswechsel mit anderen Mitteln als verwalteten Methoden erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="c166a-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c166a-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c166a-146">See also</span></span>

- [<span data-ttu-id="c166a-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c166a-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c166a-148">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c166a-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c166a-149">\<legacyImpersonationPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="c166a-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
