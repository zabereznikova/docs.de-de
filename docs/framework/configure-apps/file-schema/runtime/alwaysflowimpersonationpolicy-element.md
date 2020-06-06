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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154482"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="1ab33-102">\<alwaysFlowImpersonationPolicy>-Element</span><span class="sxs-lookup"><span data-stu-id="1ab33-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="1ab33-103">Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1ab33-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
## <a name="syntax"></a><span data-ttu-id="1ab33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ab33-104">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ab33-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1ab33-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1ab33-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ab33-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ab33-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="1ab33-107">Attributes</span></span>  
  
|<span data-ttu-id="1ab33-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1ab33-108">Attribute</span></span>|<span data-ttu-id="1ab33-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ab33-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1ab33-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="1ab33-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="1ab33-111">Gibt an, ob die Windows-Identität über asynchrone Punkte hinweg verläuft.</span><span class="sxs-lookup"><span data-stu-id="1ab33-111">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1ab33-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="1ab33-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="1ab33-113">Wert</span><span class="sxs-lookup"><span data-stu-id="1ab33-113">Value</span></span>|<span data-ttu-id="1ab33-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ab33-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1ab33-115">Die Windows-Identität fließt nicht über asynchrone Punkte, es sei denn, der Identitätswechsel wird über verwaltete Methoden wie ausgeführt <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> .</span><span class="sxs-lookup"><span data-stu-id="1ab33-115">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="1ab33-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1ab33-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1ab33-117">Die Windows-Identität verläuft immer über asynchrone Punkte, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1ab33-117">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ab33-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ab33-118">Child Elements</span></span>  
 <span data-ttu-id="1ab33-119">Keine</span><span class="sxs-lookup"><span data-stu-id="1ab33-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ab33-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ab33-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1ab33-121">Element</span><span class="sxs-lookup"><span data-stu-id="1ab33-121">Element</span></span>|<span data-ttu-id="1ab33-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ab33-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1ab33-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1ab33-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1ab33-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1ab33-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ab33-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1ab33-125">Remarks</span></span>  
 <span data-ttu-id="1ab33-126">In den .NET Framework Versionen 1,0 und 1,1 wird die Windows-Identität nicht über asynchrone Punkte hinweg übertragen.</span><span class="sxs-lookup"><span data-stu-id="1ab33-126">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="1ab33-127">In der .NET Framework Version 2,0 ist ein Objekt vorhanden, <xref:System.Threading.ExecutionContext> das Informationen über den derzeit ausgeführten Thread enthält und über asynchrone Punkte innerhalb einer Anwendungsdomäne fließt.</span><span class="sxs-lookup"><span data-stu-id="1ab33-127">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="1ab33-128">Der <xref:System.Security.Principal.WindowsIdentity> fließt auch als Teil der Informationen, die über die asynchronen Punkte hinweg fließen, vorausgesetzt, der Identitätswechsel wurde mithilfe verwalteter Methoden wie z <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> . b. und nicht über andere Mittel (z. b. Platt Form Aufrufe auf Native Methoden) erreicht.</span><span class="sxs-lookup"><span data-stu-id="1ab33-128">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="1ab33-129">Mit diesem Element wird angegeben, dass die Windows-Identität unabhängig davon, wie der Identitätswechsel erfolgt ist, über asynchrone Punkte hinweg erfolgt.</span><span class="sxs-lookup"><span data-stu-id="1ab33-129">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="1ab33-130">Sie können dieses Standardverhalten auf zwei verschiedene Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="1ab33-130">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="1ab33-131">In verwaltetem Code auf Thread Basis.</span><span class="sxs-lookup"><span data-stu-id="1ab33-131">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="1ab33-132">Sie können den Flow auf Thread Basis unterdrücken, indem Sie die <xref:System.Threading.ExecutionContext> -Einstellung und die- <xref:System.Security.SecurityContext> Einstellung mithilfe der- <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> ,-oder-Methode ändern <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1ab33-132">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="1ab33-133">Im aufzurufenden Befehl an die nicht verwaltete Hostingschnittstelle zum Laden der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1ab33-133">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="1ab33-134">Wenn eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag im Aufrufen der [CorBindToRuntimeEx-Funktions](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion angeben.</span><span class="sxs-lookup"><span data-stu-id="1ab33-134">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="1ab33-135">Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie den- `flags` Parameter für die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf fest `STARTUP_ALWAYSFLOW_IMPERSONATION` .</span><span class="sxs-lookup"><span data-stu-id="1ab33-135">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1ab33-136">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="1ab33-136">Configuration File</span></span>  
 <span data-ttu-id="1ab33-137">In einer .NET Framework Anwendung kann dieses Element nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ab33-137">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="1ab33-138">Bei einer ASP.NET-Anwendung kann der Identitätswechsel in der ASPNET. config-Datei konfiguriert werden, die im \<Windows Folder> Verzeichnis \Microsoft.NET\Framework\vx.x.xxxx enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1ab33-138">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="1ab33-139">ASP.net deaktiviert den Identitätswechsel in der Datei Aspnet. config standardmäßig mithilfe der folgenden Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="1ab33-139">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="1ab33-140">Wenn Sie in ASP.NET den Fluss des Identitäts Wechsels zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="1ab33-140">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="1ab33-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ab33-141">Example</span></span>  
 <span data-ttu-id="1ab33-142">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Windows-Identität über asynchrone Punkte hinweg verläuft, auch wenn der Identitätswechsel durch andere Mittel als verwaltete Methoden erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="1ab33-142">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ab33-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ab33-143">See also</span></span>

- [<span data-ttu-id="1ab33-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="1ab33-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1ab33-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="1ab33-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1ab33-146">\<legacyImpersonationPolicy>Gewisses</span><span class="sxs-lookup"><span data-stu-id="1ab33-146">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
