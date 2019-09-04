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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 164492eb1abc7329481f158963118b47d2c4aebc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252862"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="3550f-102">\<alwaysFlowImpersonationPolicy-> Element</span><span class="sxs-lookup"><span data-stu-id="3550f-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="3550f-103">Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3550f-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="3550f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3550f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3550f-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3550f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3550f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<alwaysFlowImpersonationPolicy>** </span><span class="sxs-lookup"><span data-stu-id="3550f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="3550f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3550f-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3550f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3550f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3550f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3550f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3550f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3550f-110">Attributes</span></span>  
  
|<span data-ttu-id="3550f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="3550f-111">Attribute</span></span>|<span data-ttu-id="3550f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3550f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3550f-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="3550f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3550f-114">Gibt an, ob die Windows-Identität über asynchrone Punkte hinweg verläuft.</span><span class="sxs-lookup"><span data-stu-id="3550f-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3550f-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="3550f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3550f-116">Wert</span><span class="sxs-lookup"><span data-stu-id="3550f-116">Value</span></span>|<span data-ttu-id="3550f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3550f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3550f-118">Die Windows-Identität fließt nicht über asynchrone Punkte, es sei denn, der Identitätswechsel wird über verwaltete Methoden <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>wie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3550f-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="3550f-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="3550f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="3550f-120">Die Windows-Identität verläuft immer über asynchrone Punkte, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3550f-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3550f-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3550f-121">Child Elements</span></span>  
 <span data-ttu-id="3550f-122">Keine</span><span class="sxs-lookup"><span data-stu-id="3550f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3550f-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3550f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3550f-124">Element</span><span class="sxs-lookup"><span data-stu-id="3550f-124">Element</span></span>|<span data-ttu-id="3550f-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3550f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3550f-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3550f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3550f-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3550f-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3550f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3550f-128">Remarks</span></span>  
 <span data-ttu-id="3550f-129">In den .NET Framework Versionen 1,0 und 1,1 wird die Windows-Identität nicht über asynchrone Punkte hinweg übertragen.</span><span class="sxs-lookup"><span data-stu-id="3550f-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="3550f-130">In der .NET Framework Version 2,0 ist ein <xref:System.Threading.ExecutionContext> Objekt vorhanden, das Informationen über den derzeit ausgeführten Thread enthält und über asynchrone Punkte innerhalb einer Anwendungsdomäne fließt.</span><span class="sxs-lookup"><span data-stu-id="3550f-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="3550f-131">Der <xref:System.Security.Principal.WindowsIdentity> fließt auch als Teil der Informationen, die über die asynchronen Punkte hinweg fließen, vorausgesetzt, der Identitätswechsel wurde mithilfe verwalteter <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> Methoden wie z. b. und nicht über andere Mittel (z. b. Platt Form Aufrufe auf Native Methoden) erreicht.</span><span class="sxs-lookup"><span data-stu-id="3550f-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="3550f-132">Mit diesem Element wird angegeben, dass die Windows-Identität unabhängig davon, wie der Identitätswechsel erfolgt ist, über asynchrone Punkte hinweg erfolgt.</span><span class="sxs-lookup"><span data-stu-id="3550f-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="3550f-133">Sie können dieses Standardverhalten auf zwei verschiedene Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="3550f-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="3550f-134">In verwaltetem Code auf Thread Basis.</span><span class="sxs-lookup"><span data-stu-id="3550f-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="3550f-135">Sie können den Flow auf Thread Basis unterdrücken, indem Sie <xref:System.Threading.ExecutionContext> die-Einstellung und die-Einstellung mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>- <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> , <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>-oder- <xref:System.Security.SecurityContext> Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="3550f-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="3550f-136">Im aufzurufenden Befehl an die nicht verwaltete Hostingschnittstelle zum Laden der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3550f-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="3550f-137">Wenn eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag im Aufrufen der [CorBindToRuntimeEx-Funktions](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion angeben.</span><span class="sxs-lookup"><span data-stu-id="3550f-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="3550f-138">Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, `flags` legen Sie den-Parameter für die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf `STARTUP_ALWAYSFLOW_IMPERSONATION`fest.</span><span class="sxs-lookup"><span data-stu-id="3550f-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="3550f-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="3550f-139">Configuration File</span></span>  
 <span data-ttu-id="3550f-140">In einer .NET Framework Anwendung kann dieses Element nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3550f-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="3550f-141">Bei einer ASP.NET-Anwendung kann der Identitätswechsel in der Datei "ASPNET. config" konfiguriert werden, die \<sich im Windows-Ordner > Verzeichnis "\Microsoft.NET\Framework\vx.x.xxxx" befindet.</span><span class="sxs-lookup"><span data-stu-id="3550f-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="3550f-142">ASP.net deaktiviert den Identitätswechsel in der Datei Aspnet. config standardmäßig mithilfe der folgenden Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="3550f-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="3550f-143">Wenn Sie in ASP.NET den Fluss des Identitäts Wechsels zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="3550f-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="3550f-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3550f-144">Example</span></span>  
 <span data-ttu-id="3550f-145">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Windows-Identität über asynchrone Punkte hinweg verläuft, auch wenn der Identitätswechsel durch andere Mittel als verwaltete Methoden erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="3550f-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3550f-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3550f-146">See also</span></span>

- [<span data-ttu-id="3550f-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="3550f-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3550f-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="3550f-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3550f-149">\<Legacy-Identitätswechsel Richtlinien-> Element</span><span class="sxs-lookup"><span data-stu-id="3550f-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
