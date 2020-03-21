---
title: <loadFromRemoteSources>-Element
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154061"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="34feb-102">\<loadFromRemoteSources>-Element</span><span class="sxs-lookup"><span data-stu-id="34feb-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="34feb-103">Gibt an, ob Assemblys, die aus Remotequellen geladen werden, in .NET Framework 4 und höher volle Vertrauenswürdigkeit gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34feb-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34feb-104">Wenn Sie aufgrund einer Fehlermeldung in der Visual Studio-Projektfehlerliste oder eines Buildfehlers zu diesem Artikel weitergeleitet wurden, finden Sie weitere Informationen unter [Gewusst wie: Verwenden einer Assembly aus dem Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="34feb-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="34feb-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34feb-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34feb-106">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="34feb-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="34feb-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span><span class="sxs-lookup"><span data-stu-id="34feb-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34feb-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="34feb-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34feb-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34feb-109">Attributes and elements</span></span>
 <span data-ttu-id="34feb-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34feb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34feb-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="34feb-111">Attributes</span></span>  
  
|<span data-ttu-id="34feb-112">attribute</span><span class="sxs-lookup"><span data-stu-id="34feb-112">Attribute</span></span>|<span data-ttu-id="34feb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34feb-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="34feb-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="34feb-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="34feb-115">Gibt an, ob einer Assembly, die von einer Remotequelle geladen wird, volle Vertrauenswürdigkeit gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34feb-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="34feb-116">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="34feb-116">enabled attribute</span></span>  
  
|<span data-ttu-id="34feb-117">value</span><span class="sxs-lookup"><span data-stu-id="34feb-117">Value</span></span>|<span data-ttu-id="34feb-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34feb-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="34feb-119">Gewähren Sie Anwendungen aus Remotequellen keine volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="34feb-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="34feb-120">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="34feb-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="34feb-121">Gewähren Sie Anwendungen aus Remotequellen volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="34feb-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34feb-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34feb-122">Child elements</span></span>  
 <span data-ttu-id="34feb-123">Keine.</span><span class="sxs-lookup"><span data-stu-id="34feb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34feb-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34feb-124">Parent elements</span></span>  
  
|<span data-ttu-id="34feb-125">Element</span><span class="sxs-lookup"><span data-stu-id="34feb-125">Element</span></span>|<span data-ttu-id="34feb-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34feb-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34feb-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="34feb-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="34feb-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="34feb-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34feb-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="34feb-129">Remarks</span></span>

<span data-ttu-id="34feb-130">Wenn Sie in der .NET Framework 3.5- und früheren Version eine Assembly von einem Remotespeicherort laden, wird Code in der Assembly in teilweiser Vertrauenswürdigkeit mit einem Grantsatz ausgeführt, der von der Zone abhängt, aus der sie geladen wird.</span><span class="sxs-lookup"><span data-stu-id="34feb-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="34feb-131">Wenn Sie beispielsweise eine Assembly von einer Website laden, wird sie in die Internetzone geladen und dem Internetberechtigungssatz erteilt.</span><span class="sxs-lookup"><span data-stu-id="34feb-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="34feb-132">Mit anderen Worten, es wird in einer Internet-Sandbox ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34feb-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="34feb-133">Ab der .NET Framework 4-Richtlinie wird die Cas-Richtlinie (Code Access Security) deaktiviert, und Assemblys werden in voller Vertrauenswürdigkeit geladen.</span><span class="sxs-lookup"><span data-stu-id="34feb-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="34feb-134">Normalerweise würde dies Assemblys, die mit der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> zuvor sandkastenten Methode geladen wurden, volle Vertrauenswürdigkeit gewähren.</span><span class="sxs-lookup"><span data-stu-id="34feb-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="34feb-135">Um dies zu verhindern, ist die Möglichkeit, Code in Assemblys auszuführen, die von einer Remotequelle geladen werden, standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="34feb-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="34feb-136">Wenn Sie versuchen, eine Remoteassembly zu <xref:System.IO.FileLoadException> laden, wird standardmäßig eine Ausnahmemeldung wie die folgende ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="34feb-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="34feb-137">Um die Assembly zu laden und ihren Code auszuführen, müssen Sie entweder Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="34feb-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="34feb-138">Explizit ecreate eine Sandbox für die Assembly (siehe [Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="34feb-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="34feb-139">Führen Sie den Code der Assembly in voller Vertrauenswürdigkeit aus.</span><span class="sxs-lookup"><span data-stu-id="34feb-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="34feb-140">Dazu konfigurieren Sie `<loadFromRemoteSources>` das Element.</span><span class="sxs-lookup"><span data-stu-id="34feb-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="34feb-141">Sie können angeben, dass die Assemblys, die in früheren Versionen von .NET Framework teilweise vertrauenswürdig ausgeführt werden, jetzt in der .NET Framework 4- und höher-Version als voll vertrauenswürdig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="34feb-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34feb-142">Wenn die Assembly nicht in voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Konfigurationselement nicht fest.</span><span class="sxs-lookup"><span data-stu-id="34feb-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="34feb-143">Erstellen Sie stattdessen eine <xref:System.AppDomain> Sandbox, in die die Baugruppe geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="34feb-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="34feb-144">Das `enabled` Attribut `<loadFromRemoteSources>` für das Element ist nur wirksam, wenn die Codezugriffssicherheit (Code Access Security, CAS) deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="34feb-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="34feb-145">Standardmäßig ist die CAS-Richtlinie in der .NET Framework 4- und höher-Version deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="34feb-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="34feb-146">Wenn Sie `enabled` `true`auf festlegen, wird Remoteassemblys volle Vertrauenswürdigkeit gewährt.</span><span class="sxs-lookup"><span data-stu-id="34feb-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="34feb-147">Wenn `enabled` nicht auf `true`gesetzt <xref:System.IO.FileLoadException> ist, wird a unter einer der folgenden Bedingungen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="34feb-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="34feb-148">Das Sandboxing-Verhalten der aktuellen Domäne unterscheidet sich von ihrem Verhalten in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="34feb-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="34feb-149">Dazu muss die CAS-Richtlinie deaktiviert und die aktuelle Domäne nicht sandkastenweise.</span><span class="sxs-lookup"><span data-stu-id="34feb-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="34feb-150">Die geladene Assembly stammt `MyComputer` nicht aus der Zone.</span><span class="sxs-lookup"><span data-stu-id="34feb-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="34feb-151">Festlegen `<loadFromRemoteSources>` des `true` Elements, dass diese Ausnahme nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="34feb-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="34feb-152">Sie können angeben, dass Sie sich nicht auf die Common Language-Laufzeit verlassen, um die geladenen Assemblys zur Sicherheit zu sandboxen, und dass sie in voller Vertrauenswürdigkeit ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="34feb-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="34feb-153">Notizen</span><span class="sxs-lookup"><span data-stu-id="34feb-153">Notes</span></span>

- <span data-ttu-id="34feb-154">In der Version .NET Framework 4.5 und höher werden Assemblys auf lokalen Netzwerkfreigaben standardmäßig als voll vertrauenswürdig ausgeführt. Sie müssen das `<loadFromRemoteSources>` Element nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="34feb-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="34feb-155">Wenn eine Anwendung aus dem Web kopiert wurde, wird sie von Windows als Webanwendung gekennzeichnet, auch wenn sie sich auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="34feb-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="34feb-156">Sie können diese Bezeichnung ändern, indem Sie ihre `<loadFromRemoteSources>` Dateieigenschaften ändern, oder Sie können das Element verwenden, um der Assembly volle Vertrauenswürdigkeit zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="34feb-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="34feb-157">Alternativ können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> Methode verwenden, um eine lokale Assembly zu laden, die vom Betriebssystem als aus dem Web geladen gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="34feb-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="34feb-158">Möglicherweise erhalten <xref:System.IO.FileLoadException> Sie eine in einer Anwendung, die in einer Windows Virtual PC-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34feb-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="34feb-159">Dies kann passieren, wenn Sie versuchen, eine Datei aus verknüpften Ordnern auf dem Hostingcomputer zu laden.</span><span class="sxs-lookup"><span data-stu-id="34feb-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="34feb-160">Sie kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner zu laden, der über [Remotedesktopdienste](/windows/win32/termserv/terminal-services-portal) (Terminaldienste) verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="34feb-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="34feb-161">Um die Ausnahme `enabled` zu `true`vermeiden, legen Sie auf fest.</span><span class="sxs-lookup"><span data-stu-id="34feb-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="34feb-162">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="34feb-162">Configuration file</span></span>

<span data-ttu-id="34feb-163">Dieses Element wird in der Regel in der Anwendungskonfigurationsdatei verwendet, kann jedoch je nach Kontext in anderen Konfigurationsdateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34feb-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="34feb-164">Weitere Informationen finden Sie im Artikel [Weitere implizite Verwendungen von CAS-Richtlinien: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) im .NET Security-Blog.</span><span class="sxs-lookup"><span data-stu-id="34feb-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="34feb-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34feb-165">Example</span></span>

<span data-ttu-id="34feb-166">Das folgende Beispiel zeigt, wie Assemblys, die aus Remotequellen geladen werden, volle Vertrauenswürdigkeit gewähren.</span><span class="sxs-lookup"><span data-stu-id="34feb-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="34feb-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34feb-167">See also</span></span>

- [<span data-ttu-id="34feb-168">Implizitere Verwendungen der CAS-Richtlinie: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="34feb-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="34feb-169">Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox</span><span class="sxs-lookup"><span data-stu-id="34feb-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="34feb-170">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="34feb-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="34feb-171">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="34feb-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
