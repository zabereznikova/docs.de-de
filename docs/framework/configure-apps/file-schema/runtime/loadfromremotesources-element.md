---
title: '&lt;LoadFromRemoteSources&gt; Element'
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a8858059159edddb4456561719c572fb9268be7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509482"
---
# <a name="ltloadfromremotesourcesgt-element"></a><span data-ttu-id="f2a95-102">&lt;LoadFromRemoteSources&gt; Element</span><span class="sxs-lookup"><span data-stu-id="f2a95-102">&lt;loadFromRemoteSources&gt; element</span></span>
<span data-ttu-id="f2a95-103">Gibt an, ob Assemblys aus Remotequellen geladen volle Vertrauenswürdigkeit in .NET Framework 4 und höher gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2a95-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f2a95-104">Wenn Sie aufgrund einer Fehlermeldung in der Fehlerliste von Visual Studio-Projekt oder einen Buildfehler zu diesem Thema weitergeleitet wurden, finden Sie unter [Vorgehensweise: Verwenden Sie eine Assembly aus dem Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="f2a95-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="f2a95-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f2a95-105">\<configuration></span></span>  
<span data-ttu-id="f2a95-106">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="f2a95-106">\<runtime></span></span>  
<span data-ttu-id="f2a95-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="f2a95-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2a95-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2a95-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2a95-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f2a95-109">Attributes and elements</span></span>
 <span data-ttu-id="f2a95-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2a95-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2a95-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f2a95-111">Attributes</span></span>  
  
|<span data-ttu-id="f2a95-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="f2a95-112">Attribute</span></span>|<span data-ttu-id="f2a95-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2a95-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f2a95-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f2a95-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="f2a95-115">Gibt an, ob eine Assembly, die von einer Remotequelle geladen wird, volle Vertrauenswürdigkeit gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2a95-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f2a95-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="f2a95-116">enabled attribute</span></span>  
  
|<span data-ttu-id="f2a95-117">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a95-117">Value</span></span>|<span data-ttu-id="f2a95-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2a95-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f2a95-119">Gewähren Sie volle Vertrauenswürdigkeit nicht auf Anwendungen aus Remotequellen.</span><span class="sxs-lookup"><span data-stu-id="f2a95-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="f2a95-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f2a95-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="f2a95-121">Gewähren Sie volle Vertrauenswürdigkeit auf Anwendungen aus Remotequellen.</span><span class="sxs-lookup"><span data-stu-id="f2a95-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2a95-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2a95-122">Child elements</span></span>  
 <span data-ttu-id="f2a95-123">Keine</span><span class="sxs-lookup"><span data-stu-id="f2a95-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2a95-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2a95-124">Parent elements</span></span>  
  
|<span data-ttu-id="f2a95-125">Element</span><span class="sxs-lookup"><span data-stu-id="f2a95-125">Element</span></span>|<span data-ttu-id="f2a95-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2a95-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f2a95-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f2a95-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f2a95-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="f2a95-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2a95-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2a95-129">Remarks</span></span>

<span data-ttu-id="f2a95-130">Wenn Sie eine Assembly von einem Remotestandort befindet, Laden in das .NET Framework 3.5 und früheren Versionen wird Code in der Assembly bei teilweiser Vertrauenswürdigkeit mit einem Berechtigungssatz, der die Zone hängt von dem es geladen wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f2a95-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="f2a95-131">Z. B. Wenn Sie eine Assembly von einer Website laden, handelt es sich dabei in der Internetzone geladen den Internet-Berechtigungssatz.</span><span class="sxs-lookup"><span data-stu-id="f2a95-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="f2a95-132">Das heißt, führt er in einem Internet-Sandkasten.</span><span class="sxs-lookup"><span data-stu-id="f2a95-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="f2a95-133">Ab .NET Framework 4, Richtlinie für die Codezugriffssicherheit (CAS) ist deaktiviert, und Assemblys mit voller Vertrauenswürdigkeit geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f2a95-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="f2a95-134">Normalerweise würde diese Assemblys geladen und volle Vertrauenswürdigkeit gewähren der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> Methode, die zuvor Sandbox waren.</span><span class="sxs-lookup"><span data-stu-id="f2a95-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="f2a95-135">Um dies zu verhindern, ist die Möglichkeit zum Ausführen von Code in Assemblys, die von einer Remotequelle geladen, standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2a95-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="f2a95-136">Standardmäßig, wenn Sie versuchen, eine Remoteassembly, laden ein <xref:System.IO.FileLoadException> mit eine Ausnahmemeldung wie, dass Sie Folgendes ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="f2a95-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="f2a95-137">Zum Laden der Assembly und deren Code ausführen, müssen Sie entweder:</span><span class="sxs-lookup"><span data-stu-id="f2a95-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="f2a95-138">Erstellen Sie explizit einen Sandkasten für die Assembly (finden Sie unter [wie: Ausführen von teilweise vertrauenswürdigen Code in einer Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="f2a95-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="f2a95-139">Führen Sie Code von der Assembly mit voller Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="f2a95-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="f2a95-140">Konfigurieren Sie dazu die `<loadFromRemoteSources>` Element.</span><span class="sxs-lookup"><span data-stu-id="f2a95-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="f2a95-141">Sie können angeben, dass die Assemblys, die bei teilweiser Vertrauenswürdigkeit in früheren Versionen von .NET Framework ausgeführt werden jetzt als voll vertrauenswürdig in der .NET Framework 4 und höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="f2a95-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2a95-142">Wenn die Assembly nicht mit voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Element nicht.</span><span class="sxs-lookup"><span data-stu-id="f2a95-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="f2a95-143">Erstellen Sie stattdessen eine Sandbox <xref:System.AppDomain> in dem die Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="f2a95-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="f2a95-144">Die `enabled` -Attribut für die `<loadFromRemoteSources>` Element gilt nur, wenn die Codezugriffssicherheit (CAS) deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f2a95-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="f2a95-145">Standardmäßig ist die CAS-Richtlinie in der .NET Framework 4 und höheren Versionen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2a95-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="f2a95-146">Setzen Sie `enabled` zu `true`, remote-Assemblys die volle Vertrauenswürdigkeit gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a95-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="f2a95-147">Wenn `enabled` ist nicht festgelegt, um `true`, <xref:System.IO.FileLoadException> wird in einer der folgenden Bedingungen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="f2a95-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="f2a95-148">Der Sandkasten-Verhalten der aktuellen Domäne unterscheidet sich vom Verhalten in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="f2a95-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="f2a95-149">Dies erfordert die CAS-Richtlinie deaktiviert werden soll, und der aktuellen Domäne nicht zu Sandbox.</span><span class="sxs-lookup"><span data-stu-id="f2a95-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="f2a95-150">Die geladene Assembly stammt nicht von der `MyComputer` Zone.</span><span class="sxs-lookup"><span data-stu-id="f2a95-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="f2a95-151">Festlegen der `<loadFromRemoteSources>` Element `true` wird verhindert, dass diese Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f2a95-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="f2a95-152">Damit können Sie angeben, dass nicht Sie sich die common Language Runtime für das Sandboxing die geladenen Assemblys für die Sicherheit verlassen und ermöglicht werden kann. Führen Sie in volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="f2a95-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="f2a95-153">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2a95-153">Notes</span></span>

- <span data-ttu-id="f2a95-154">In der .NET Framework 4.5 und höheren Versionen wird standardmäßig Assemblys auf der lokalen Netzwerkfreigaben mit voller Vertrauenswürdigkeit ausgeführt; Sie müssen keine aktivieren die `<loadFromRemoteSources>` Element.</span><span class="sxs-lookup"><span data-stu-id="f2a95-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="f2a95-155">Wenn eine Anwendung über das Web kopiert wurde, wird er von Windows als replikationsbereit markiert eine Webanwendung, auch wenn er auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="f2a95-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="f2a95-156">Sie können diese Bezeichnung durch Ändern der Dateieigenschaften ändern, oder Sie können die `<loadFromRemoteSources>` Element gewähren Sie die Assembly volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="f2a95-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="f2a95-157">Als Alternative können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> Methode, um eine lokale Assembly zu laden, die das Betriebssystem gekennzeichnet wurden, als aus dem Web geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f2a95-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="f2a95-158">Sie erhalten möglicherweise eine <xref:System.IO.FileLoadException> in einer Anwendung, die in einer Windows Virtual PC-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2a95-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="f2a95-159">Dies kann passieren, wenn Sie versuchen, eine Datei aus dem verknüpften Ordner auf dem Hostcomputer zu laden.</span><span class="sxs-lookup"><span data-stu-id="f2a95-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="f2a95-160">Er kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner, die über verknüpfte laden [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminaldienste).</span><span class="sxs-lookup"><span data-stu-id="f2a95-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="f2a95-161">Um die Ausnahme zu vermeiden, legen Sie `enabled` zu `true`.</span><span class="sxs-lookup"><span data-stu-id="f2a95-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="f2a95-162">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f2a95-162">Configuration file</span></span>

<span data-ttu-id="f2a95-163">Dieses Element wird in der Regel in der Konfigurationsdatei der Anwendung verwendet, aber in anderen Konfigurationsdateien, die je nach Kontext verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2a95-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="f2a95-164">Weitere Informationen finden Sie im Artikel [Weitere implizite verwendet der CAS-Richtlinie: LoadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) im .NET Security Blog.</span><span class="sxs-lookup"><span data-stu-id="f2a95-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="f2a95-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2a95-165">Example</span></span>

<span data-ttu-id="f2a95-166">Das folgende Beispiel zeigt, wie Sie Assemblys aus Remotequellen geladen volles Vertrauen gewähren.</span><span class="sxs-lookup"><span data-stu-id="f2a95-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="f2a95-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2a95-167">See also</span></span>

[<span data-ttu-id="f2a95-168">Mehr impliziten verwendet der CAS-Richtlinie: LoadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="f2a95-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)  
[<span data-ttu-id="f2a95-169">How to: Run Partially Trusted Code in a Sandbox (Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten)</span><span class="sxs-lookup"><span data-stu-id="f2a95-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
[<span data-ttu-id="f2a95-170">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="f2a95-170">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
[<span data-ttu-id="f2a95-171">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f2a95-171">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
