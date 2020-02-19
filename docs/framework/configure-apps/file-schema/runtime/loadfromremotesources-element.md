---
title: <loadFromRemoteSources>-Element
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: 454314bf1002a9648f669cc708c8ac42461fccaf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452265"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="a1346-102">\<loadFromRemoteSources-> Element</span><span class="sxs-lookup"><span data-stu-id="a1346-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="a1346-103">Gibt an, ob aus Remote Quellen geladene Assemblys in .NET Framework 4 und höher volle Vertrauenswürdigkeit gewährt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a1346-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1346-104">Wenn Sie aufgrund einer Fehlermeldung in der Visual Studio-Projekt Fehlerliste oder einem Buildfehler zu diesem Artikel weitergeleitet wurden, finden Sie weitere Informationen unter Gewusst [wie: Verwenden einer Assembly aus dem Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a1346-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="a1346-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a1346-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a1346-106">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a1346-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a1346-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<loadFromRemoteSources >**</span><span class="sxs-lookup"><span data-stu-id="a1346-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1346-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1346-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1346-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1346-109">Attributes and elements</span></span>
 <span data-ttu-id="a1346-110">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1346-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1346-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1346-111">Attributes</span></span>  
  
|<span data-ttu-id="a1346-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="a1346-112">Attribute</span></span>|<span data-ttu-id="a1346-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1346-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a1346-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a1346-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a1346-115">Gibt an, ob einer Assembly, die aus einer Remote Quelle geladen wird, volle Vertrauenswürdigkeit gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1346-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a1346-116">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="a1346-116">enabled attribute</span></span>  
  
|<span data-ttu-id="a1346-117">Wert</span><span class="sxs-lookup"><span data-stu-id="a1346-117">Value</span></span>|<span data-ttu-id="a1346-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1346-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a1346-119">Gewähren Sie Anwendungen aus Remote Quellen keine volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="a1346-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="a1346-120">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="a1346-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a1346-121">Gewähren Sie Anwendungen aus Remote Quellen volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="a1346-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1346-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1346-122">Child elements</span></span>  
 <span data-ttu-id="a1346-123">None.</span><span class="sxs-lookup"><span data-stu-id="a1346-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1346-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1346-124">Parent elements</span></span>  
  
|<span data-ttu-id="a1346-125">Element</span><span class="sxs-lookup"><span data-stu-id="a1346-125">Element</span></span>|<span data-ttu-id="a1346-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1346-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a1346-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a1346-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a1346-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="a1346-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1346-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1346-129">Remarks</span></span>

<span data-ttu-id="a1346-130">Wenn Sie in der .NET Framework 3,5 und früheren Versionen eine Assembly von einem Remote Speicherort laden, wird der Code in der Assembly mit teilweiser Vertrauenswürdigkeit mit einem Berechtigungs Satz ausgeführt, der von der Zone abhängig ist, aus der er geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a1346-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="a1346-131">Wenn Sie z. b. eine Assembly von einer Website laden, wird Sie in die Internet Zone geladen und erhält den Internet Berechtigungs Satz.</span><span class="sxs-lookup"><span data-stu-id="a1346-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="a1346-132">Das heißt, Sie wird in einer Internet Sandbox ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a1346-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="a1346-133">Ab .NET Framework 4 ist die Richtlinie für die Code Zugriffssicherheit (Code Access Security, CAS) deaktiviert, und Assemblys werden mit voller Vertrauenswürdigkeit geladen.</span><span class="sxs-lookup"><span data-stu-id="a1346-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="a1346-134">Normalerweise würde dadurch eine volle Vertrauenswürdigkeit für Assemblys gewährt werden, die mit der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Methode geladen werden, die zuvor in einem Sandkasten</span><span class="sxs-lookup"><span data-stu-id="a1346-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="a1346-135">Um dies zu verhindern, ist die Möglichkeit, Code in aus einer Remote Quelle geladenen Assemblys auszuführen, standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a1346-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="a1346-136">Wenn Sie versuchen, eine Remoteassembly zu laden, wird standardmäßig eine <xref:System.IO.FileLoadException> mit einer Ausnahme Meldung wie der folgenden ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="a1346-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="a1346-137">Um die Assembly zu laden und Ihren Code auszuführen, müssen Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="a1346-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="a1346-138">Erstellen Sie explizit eine Sandbox für die Assembly (Weitere Informationen finden [Sie unter Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="a1346-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="a1346-139">Führen Sie den Assemblycode in voller Vertrauenswürdigkeit aus.</span><span class="sxs-lookup"><span data-stu-id="a1346-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="a1346-140">Dazu konfigurieren Sie das `<loadFromRemoteSources>`-Element.</span><span class="sxs-lookup"><span data-stu-id="a1346-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="a1346-141">Mit dieser Einstellung können Sie angeben, dass die Assemblys, die in früheren Versionen des .NET Framework in teilweiser Vertrauenswürdigkeit ausgeführt werden, nun in der .NET Framework 4 und höheren Versionen mit voller Vertrauenswürdigkeit ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="a1346-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1346-142">Wenn die Assembly nicht mit voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Konfigurationselement nicht fest.</span><span class="sxs-lookup"><span data-stu-id="a1346-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="a1346-143">Erstellen Sie stattdessen einen Sandkasten <xref:System.AppDomain>, in dem die Assembly geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1346-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="a1346-144">Das `enabled`-Attribut für das `<loadFromRemoteSources>`-Element ist nur wirksam, wenn die Code Zugriffssicherheit (Code Access Security, CAS) deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a1346-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="a1346-145">Standardmäßig ist die CAS-Richtlinie in den .NET Framework 4 und höheren Versionen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a1346-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="a1346-146">Wenn Sie `enabled` auf `true`festlegen, wird Remoteassemblys volle Vertrauenswürdigkeit gewährt.</span><span class="sxs-lookup"><span data-stu-id="a1346-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="a1346-147">Wenn `enabled` nicht auf `true`festgelegt ist, wird unter den folgenden Bedingungen eine <xref:System.IO.FileLoadException> ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="a1346-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="a1346-148">Das Sandkasten Verhalten der aktuellen Domäne unterscheidet sich vom Verhalten in der .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="a1346-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="a1346-149">Hierfür muss die CAS-Richtlinie deaktiviert werden, und die aktuelle Domäne darf nicht als Sandkasten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a1346-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="a1346-150">Die Assembly, die geladen wird, befindet sich nicht aus der `MyComputer` Zone.</span><span class="sxs-lookup"><span data-stu-id="a1346-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="a1346-151">Wenn Sie das `<loadFromRemoteSources>`-Element auf `true` festlegen, wird verhindert, dass diese Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a1346-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="a1346-152">Sie können angeben, dass Sie sich nicht auf den Common Language Runtime verlassen, um die geladenen Assemblys auf die Sicherheit zu überführen, und dass Sie in voller Vertrauenswürdigkeit ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="a1346-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="a1346-153">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1346-153">Notes</span></span>

- <span data-ttu-id="a1346-154">In den .NET Framework 4,5 und höheren Versionen werden Assemblys auf lokalen Netzwerkfreigaben standardmäßig mit vollständiger Vertrauenswürdigkeit ausgeführt. Sie müssen das `<loadFromRemoteSources>`-Element nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a1346-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="a1346-155">Wenn eine Anwendung aus dem Web kopiert wurde, wird Sie von Windows als Webanwendung gekennzeichnet, auch wenn Sie sich auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="a1346-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="a1346-156">Sie können diese Bezeichnung ändern, indem Sie Ihre Dateieigenschaften ändern, oder Sie können das `<loadFromRemoteSources>`-Element verwenden, um der Assembly volle Vertrauenswürdigkeit zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="a1346-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="a1346-157">Als Alternative können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>-Methode verwenden, um eine lokale Assembly zu laden, die vom Betriebssystem als aus dem Web geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a1346-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="a1346-158">Sie erhalten möglicherweise eine <xref:System.IO.FileLoadException> in einer Anwendung, die in einer Windows Virtual PC-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a1346-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="a1346-159">Dies kann vorkommen, wenn Sie versuchen, eine Datei aus verknüpften Ordnern auf dem hostingcomputer zu laden.</span><span class="sxs-lookup"><span data-stu-id="a1346-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="a1346-160">Dies kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner zu laden, der über [Remotedesktopdienste](/windows/win32/termserv/terminal-services-portal) (Terminal Dienste) verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="a1346-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="a1346-161">Um die Ausnahme zu vermeiden, legen Sie `enabled` auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="a1346-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="a1346-162">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a1346-162">Configuration file</span></span>

<span data-ttu-id="a1346-163">Dieses Element wird in der Regel in der Anwendungs Konfigurationsdatei verwendet, kann aber in anderen Konfigurationsdateien verwendet werden, je nach Kontext.</span><span class="sxs-lookup"><span data-stu-id="a1346-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="a1346-164">Weitere Informationen finden Sie im Artikel zur [impliziten Verwendung der CAS-Richtlinie: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) im .net Security-Blog.</span><span class="sxs-lookup"><span data-stu-id="a1346-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="a1346-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1346-165">Example</span></span>

<span data-ttu-id="a1346-166">Im folgenden Beispiel wird gezeigt, wie Sie Assemblys, die aus Remote Quellen geladen werden, volle Vertrauenswürdigkeit gewähren</span><span class="sxs-lookup"><span data-stu-id="a1346-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="a1346-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1346-167">See also</span></span>

- [<span data-ttu-id="a1346-168">Implizitere Verwendung der CAS-Richtlinie: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="a1346-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="a1346-169">How to: Run Partially Trusted Code in a Sandbox (Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten)</span><span class="sxs-lookup"><span data-stu-id="a1346-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="a1346-170">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a1346-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a1346-171">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a1346-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
