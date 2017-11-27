---
title: '&lt;SupportPortability&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b46d12ecebae17b7cfe2168b6313be45ad5b04d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltsupportportabilitygt-element"></a><span data-ttu-id="775e7-102">&lt;SupportPortability&gt; Element</span><span class="sxs-lookup"><span data-stu-id="775e7-102">&lt;supportPortability&gt; Element</span></span>
<span data-ttu-id="775e7-103">Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="775e7-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="775e7-104">\<Konfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="775e7-104">\<configuration> Element</span></span>  
<span data-ttu-id="775e7-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="775e7-105">\<runtime> Element</span></span>  
<span data-ttu-id="775e7-106">\<AssemblyBinding >-Element</span><span class="sxs-lookup"><span data-stu-id="775e7-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="775e7-107">\<SupportPortability >-Element</span><span class="sxs-lookup"><span data-stu-id="775e7-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="775e7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="775e7-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="775e7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="775e7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="775e7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="775e7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="775e7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="775e7-111">Attributes</span></span>  
  
|<span data-ttu-id="775e7-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="775e7-112">Attribute</span></span>|<span data-ttu-id="775e7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="775e7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="775e7-114">PKT</span><span class="sxs-lookup"><span data-stu-id="775e7-114">PKT</span></span>|<span data-ttu-id="775e7-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="775e7-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="775e7-116">Gibt das öffentliche Schlüsseltoken der betreffenden Assembly als Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="775e7-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="775e7-117">enabled</span><span class="sxs-lookup"><span data-stu-id="775e7-117">enabled</span></span>|<span data-ttu-id="775e7-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="775e7-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="775e7-119">Gibt an, ob Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="775e7-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="775e7-120">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="775e7-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="775e7-121">Wert</span><span class="sxs-lookup"><span data-stu-id="775e7-121">Value</span></span>|<span data-ttu-id="775e7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="775e7-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="775e7-123">true</span><span class="sxs-lookup"><span data-stu-id="775e7-123">true</span></span>|<span data-ttu-id="775e7-124">Aktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly.</span><span class="sxs-lookup"><span data-stu-id="775e7-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="775e7-125">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="775e7-125">This is the default.</span></span>|  
|<span data-ttu-id="775e7-126">false</span><span class="sxs-lookup"><span data-stu-id="775e7-126">false</span></span>|<span data-ttu-id="775e7-127">Deaktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly.</span><span class="sxs-lookup"><span data-stu-id="775e7-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="775e7-128">Dadurch kann die Anwendung Verweise auf mehrere Implementierungen besitzen.</span><span class="sxs-lookup"><span data-stu-id="775e7-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="775e7-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="775e7-129">Child Elements</span></span>  
 <span data-ttu-id="775e7-130">Keine</span><span class="sxs-lookup"><span data-stu-id="775e7-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="775e7-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="775e7-131">Parent Elements</span></span>  
  
|<span data-ttu-id="775e7-132">Element</span><span class="sxs-lookup"><span data-stu-id="775e7-132">Element</span></span>|<span data-ttu-id="775e7-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="775e7-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="775e7-134">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="775e7-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="775e7-135">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="775e7-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="775e7-136">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="775e7-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="775e7-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="775e7-137">Remarks</span></span>  
 <span data-ttu-id="775e7-138">Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], Unterstützung für Anwendungen, die beide Implementierungen von .NET Framework verwenden, können automatisch bereitgestellt wird z. B. die Implementierung von .NET Framework oder .NET Framework for Silverlight-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="775e7-138">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="775e7-139">Die zwei Implementierungen einer bestimmten .NET Framework-Assembly werden vom Assemblybinder als äquivalent betrachtet.</span><span class="sxs-lookup"><span data-stu-id="775e7-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="775e7-140">In einigen Szenarien verursacht diese Anwendungsportabilitätsfunktion Probleme.</span><span class="sxs-lookup"><span data-stu-id="775e7-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="775e7-141">In jenen Szenarien kann das `<supportPortability>`-Element verwendet werden, um die Funktion zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="775e7-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="775e7-142">Ein solches Szenario ist eine Assembly, die sowohl die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung einer bestimmten Verweisassembly mit Verweisen versehen muss.</span><span class="sxs-lookup"><span data-stu-id="775e7-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="775e7-143">Ein in Windows Presentation Foundation (WPF) geschriebener XAML-Designer müsste möglicherweise sowohl auf die WPF-Desktopimplementierung, für die Benutzeroberfläche des Designers, als auch die Teilmenge von WPF, die in der Silverlight-Implementierung enthalten ist, verweisen.</span><span class="sxs-lookup"><span data-stu-id="775e7-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="775e7-144">Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht.</span><span class="sxs-lookup"><span data-stu-id="775e7-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="775e7-145">Dieses Element deaktiviert das Standardverhalten und ermöglicht eine erfolgreiche Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="775e7-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="775e7-146">Damit der Compiler die Informationen an die Assemblybindungs-Logik der Common Language Runtime übergibt, müssen Sie den Speicherort der Datei "app.config", die dieses Element enthält, mithilfe der `/appconfig`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="775e7-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="775e7-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="775e7-147">Example</span></span>  
 <span data-ttu-id="775e7-148">Das folgende Beispiel ermöglicht einer Anwendung, über Verweise sowohl auf die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung jeder die oft ausgegebene Befehlszeilen  .NET Framework-Assembly, die in beiden Implementierungen vorhanden ist, zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="775e7-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="775e7-149">Mit der `/appconfig`-Compileroption muss der Speicherort dieser app.config-Datei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="775e7-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="775e7-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="775e7-150">See Also</span></span>  
 [<span data-ttu-id="775e7-151">/ appconfig (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="775e7-151">/appconfig (C# Compiler Options)</span></span>](http://msdn.microsoft.com/library/ee523958.aspx)  
 [<span data-ttu-id="775e7-152">Übersicht über die Vereinheitlichung von .NET Framework-Assembly</span><span class="sxs-lookup"><span data-stu-id="775e7-152">.NET Framework Assembly Unification Overview</span></span>](http://msdn.microsoft.com/en-us/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
