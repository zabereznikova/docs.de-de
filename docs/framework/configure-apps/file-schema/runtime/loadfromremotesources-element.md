---
title: '&lt;LoadFromRemoteSources&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efb968d40e54c7552fba0a592e759f9e83c92309
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltloadfromremotesourcesgt-element"></a><span data-ttu-id="2b331-102">&lt;LoadFromRemoteSources&gt; Element</span><span class="sxs-lookup"><span data-stu-id="2b331-102">&lt;loadFromRemoteSources&gt; Element</span></span>
<span data-ttu-id="2b331-103">Gibt an, ob Assemblys Remotedatenquellen volle Vertrauenswürdigkeit gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2b331-103">Specifies whether assemblies from remote sources should be granted full trust.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b331-104">Wenn Sie eine Fehlermeldung in der Fehlerliste von Visual Studio-Projekt oder ein Buildfehler aufgrund von zu diesem Thema weitergeleitet wurden, finden Sie unter [Vorgehensweise: Verwenden Sie eine Assembly aus dem Internet in Visual Studio](http://msdn.microsoft.com/en-us/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="2b331-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](http://msdn.microsoft.com/en-us/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="2b331-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2b331-105">\<configuration></span></span>  
<span data-ttu-id="2b331-106">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="2b331-106">\<runtime></span></span>  
<span data-ttu-id="2b331-107">\<LoadFromRemoteSources ></span><span class="sxs-lookup"><span data-stu-id="2b331-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b331-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b331-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b331-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2b331-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2b331-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b331-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b331-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2b331-111">Attributes</span></span>  
  
|<span data-ttu-id="2b331-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2b331-112">Attribute</span></span>|<span data-ttu-id="2b331-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b331-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2b331-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2b331-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="2b331-115">Gibt an, ob eine Assembly, die über Remotedatenquellen geladen wird volle Vertrauenswürdigkeit gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2b331-115">Specifies whether an assembly that is loaded from remote sources should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2b331-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="2b331-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="2b331-117">Wert</span><span class="sxs-lookup"><span data-stu-id="2b331-117">Value</span></span>|<span data-ttu-id="2b331-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b331-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2b331-119">Gewähren Sie volle Vertrauenswürdigkeit nicht auf Anwendungen Remotedatenquellen.</span><span class="sxs-lookup"><span data-stu-id="2b331-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="2b331-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="2b331-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2b331-121">Gewähren Sie volle Vertrauenswürdigkeit für Anwendungen Remotedatenquellen.</span><span class="sxs-lookup"><span data-stu-id="2b331-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b331-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b331-122">Child Elements</span></span>  
 <span data-ttu-id="2b331-123">Keine</span><span class="sxs-lookup"><span data-stu-id="2b331-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b331-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b331-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2b331-125">Element</span><span class="sxs-lookup"><span data-stu-id="2b331-125">Element</span></span>|<span data-ttu-id="2b331-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b331-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2b331-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2b331-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2b331-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="2b331-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b331-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b331-129">Remarks</span></span>  
 <span data-ttu-id="2b331-130">In .NET Framework, Version 3.5 und frühere Versionen müssen, wenn Sie von einem Remotestandort aus eine Assembly geladen würde die Assembly mit einem Berechtigungssatz teilweise vertrauenswürdigen ausgeführt werden, die die Zone abhängen, in denen es geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2b331-130">In the .NET Framework version 3.5 and earlier versions, if you loaded an assembly from a remote location, the assembly would run partially trusted with a grant set that depended on the zone in which it was loaded.</span></span> <span data-ttu-id="2b331-131">Z. B. Wenn Sie von einer Website eine Assembly geladen, es wurde in der Internetzone geladen und den Internet-Berechtigungssatz gewährt.</span><span class="sxs-lookup"><span data-stu-id="2b331-131">For example, if you loaded an assembly from a website, it was loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="2b331-132">Das heißt, in der eine Internet-Sandkasten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b331-132">In other words, it executed in an Internet sandbox.</span></span> <span data-ttu-id="2b331-133">Wenn Sie versuchen, diese Assembly auszuführen, der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höheren Versionen wird eine Ausnahme ausgelöst; Sie müssen entweder explizit einen Sandkasten für die Assembly erstellen (finden Sie unter [wie: Ausführen von teilweise vertrauenswürdigen Code in einem Sandkasten](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), oder vollständiger Vertrauenswürdigkeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b331-133">If you try to run that assembly in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later versions, an exception is thrown; you must either explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), or run it in full trust.</span></span>  
  
 <span data-ttu-id="2b331-134">Die `<loadFromRemoteSources>` Element können Sie angeben, dass die Assemblys, die teilweise vertrauenswürdige in frühere Versionen von .NET Framework ausgeführt worden wäre vollständig ausgeführt werden, die im vertrauenswürdig der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="2b331-134">The `<loadFromRemoteSources>` element lets you specify that the assemblies that would have run partially trusted in earlier versions of the .NET Framework are to be run fully trusted in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="2b331-135">Standardmäßig remote Assemblys führen nicht in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher.</span><span class="sxs-lookup"><span data-stu-id="2b331-135">By default, remote assemblies do not run in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span> <span data-ttu-id="2b331-136">Um eine remote-Assembly ausführen zu können, müssen Sie es als vollständig vertrauenswürdig ausführen oder Erstellen einer Sandbox <xref:System.AppDomain> in dem er ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b331-136">To run a remote assembly, you must either run it as fully trusted or create a sandboxed <xref:System.AppDomain> in which to run it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b331-137">In der [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], Assemblys auf der lokalen Netzwerkfreigaben werden standardmäßig mit voller Vertrauenswürdigkeit ausgeführt; Sie müssen nicht zum Aktivieren der `<loadFromRemoteSources>` Element.</span><span class="sxs-lookup"><span data-stu-id="2b331-137">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], assemblies on local network shares are run as full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b331-138">Wenn eine Anwendung aus dem Web kopiert wurde, wird er von Windows gekennzeichnet als eine Web-Anwendung, auch wenn er auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="2b331-138">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="2b331-139">Sie können diese Bezeichnung durch Ändern der Dateieigenschaften ändern oder Sie können die `<loadFromRemoteSources>` Element, um die Assembly zu gewähren, volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="2b331-139">You can change that designation by changing the file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="2b331-140">Als Alternative können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> Methode, um eine lokale Assembly zu laden, die das Betriebssystem gekennzeichnet wurde, als aus dem Web geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2b331-140">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>  
  
 <span data-ttu-id="2b331-141">Die `enabled` Attribut für dieses Element wirksam ist, nur, wenn die Codezugriffssicherheit (CAS) deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2b331-141">The `enabled` attribute for this element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="2b331-142">Standardmäßig ist die CAS-Richtlinie in deaktiviert die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="2b331-142">By default, CAS policy is disabled in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="2b331-143">Wenn Sie festlegen, `enabled` zu `true`, Remoteanwendungen volle Vertrauenswürdigkeit gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="2b331-143">If you set `enabled` to `true`, remote applications are granted full trust.</span></span>  
  
 <span data-ttu-id="2b331-144">Wenn `<loadFromRemoteSources>``enabled` nicht festgelegt ist, um `true`, in den folgenden Situationen wird eine Ausnahme ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="2b331-144">If `<loadFromRemoteSources>``enabled` is not set to `true`, an exception is thrown under the following conditions:</span></span>  
  
-   <span data-ttu-id="2b331-145">Das Verwenden einer Sandboxverhalten von der aktuellen Domäne unterscheidet sich vom Verhalten in der [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b331-145">The sandboxing behavior of the current domain is different from its behavior in the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span> <span data-ttu-id="2b331-146">Dies erfordert CAS-Richtlinie deaktiviert werden soll, und der aktuellen Domäne Sandbox kann.</span><span class="sxs-lookup"><span data-stu-id="2b331-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>  
  
-   <span data-ttu-id="2b331-147">Die geladene Assembly stammt nicht von der `MyComputer` Zone.</span><span class="sxs-lookup"><span data-stu-id="2b331-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b331-148">Sie erhalten möglicherweise eine <xref:System.IO.FileLoadException> in einer Windows Virtual PC-Anwendung, wenn Sie versuchen, eine Datei aus verknüpften Ordnern auf dem Hostcomputer zu laden.</span><span class="sxs-lookup"><span data-stu-id="2b331-148">You may get a <xref:System.IO.FileLoadException> in a Windows Virtual PC application when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="2b331-149">Dieser Fehler kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner, die über verknüpfte laden [Remote Desktop Services](http://go.microsoft.com/fwlink/?LinkId=182775) (Terminaldienste).</span><span class="sxs-lookup"><span data-stu-id="2b331-149">This error may also occur when you try to load a file from a folder linked over [Remote Desktop Services](http://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="2b331-150">Um die Ausnahme zu vermeiden, legen Sie `enabled` auf `true`.</span><span class="sxs-lookup"><span data-stu-id="2b331-150">To avoid the exception, set `enabled` to `true`.</span></span>  
  
 <span data-ttu-id="2b331-151">Festlegen der `<loadFromRemoteSources>` Element `true` wird verhindert, dass diese Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="2b331-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="2b331-152">Können Sie angeben, dass Sie nicht auf die common Language Runtime für das Sandboxing geladenen Assemblys für die Sicherheit der vertrauenden Seite sind und dass sie erfolgen können, um die Ausführung als volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="2b331-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute as full trust.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2b331-153">Wenn die Assembly nicht voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Element nicht.</span><span class="sxs-lookup"><span data-stu-id="2b331-153">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="2b331-154">Erstellen Sie stattdessen eine Sandbox <xref:System.AppDomain> in dem die Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="2b331-154">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="2b331-155">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2b331-155">Configuration File</span></span>  
 <span data-ttu-id="2b331-156">Dieses Element wird in der Regel in der Anwendungskonfigurationsdatei verwendet, jedoch in andere Konfigurationsdateien, die je nach Kontext verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b331-156">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="2b331-157">Weitere Informationen finden Sie im Artikel [Weitere implizite verwendet der CAS-Richtlinie: LoadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) in .NET Security Blog.</span><span class="sxs-lookup"><span data-stu-id="2b331-157">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b331-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b331-158">Example</span></span>  
 <span data-ttu-id="2b331-159">Im folgende Beispiel wird gezeigt, wie So gewähren Sie volle Vertrauenswürdigkeit für Anwendungen Remotedatenquellen wird.</span><span class="sxs-lookup"><span data-stu-id="2b331-159">The following example shows how to grant full trust to applications from remote sources.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b331-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b331-160">See Also</span></span>  
 [<span data-ttu-id="2b331-161">Mehr impliziten Verwendungen von CAS-Richtlinie: LoadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="2b331-161">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [<span data-ttu-id="2b331-162">How to: Run Partially Trusted Code in a Sandbox (Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten)</span><span class="sxs-lookup"><span data-stu-id="2b331-162">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="2b331-163">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="2b331-163">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="2b331-164">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2b331-164">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
