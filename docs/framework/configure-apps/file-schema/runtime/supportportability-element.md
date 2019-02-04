---
title: <supportPortability>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1e1c3236ed2d79592bca46e925c9f67e5ac9c51
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675334"
---
# <a name="supportportability-element"></a><span data-ttu-id="9fda5-102">\<SupportPortability >-Element</span><span class="sxs-lookup"><span data-stu-id="9fda5-102">\<supportPortability> Element</span></span>
<span data-ttu-id="9fda5-103">Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="9fda5-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="9fda5-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="9fda5-104">\<configuration> Element</span></span>  
<span data-ttu-id="9fda5-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="9fda5-105">\<runtime> Element</span></span>  
<span data-ttu-id="9fda5-106">\<AssemblyBinding >-Element</span><span class="sxs-lookup"><span data-stu-id="9fda5-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="9fda5-107">\<SupportPortability >-Element</span><span class="sxs-lookup"><span data-stu-id="9fda5-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fda5-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fda5-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fda5-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9fda5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9fda5-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9fda5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fda5-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9fda5-111">Attributes</span></span>  
  
|<span data-ttu-id="9fda5-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="9fda5-112">Attribute</span></span>|<span data-ttu-id="9fda5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fda5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fda5-114">PKT</span><span class="sxs-lookup"><span data-stu-id="9fda5-114">PKT</span></span>|<span data-ttu-id="9fda5-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="9fda5-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="9fda5-116">Gibt das öffentliche Schlüsseltoken der betreffenden Assembly als Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="9fda5-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="9fda5-117">enabled</span><span class="sxs-lookup"><span data-stu-id="9fda5-117">enabled</span></span>|<span data-ttu-id="9fda5-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="9fda5-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9fda5-119">Gibt an, ob Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9fda5-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9fda5-120">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="9fda5-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="9fda5-121">Wert</span><span class="sxs-lookup"><span data-stu-id="9fda5-121">Value</span></span>|<span data-ttu-id="9fda5-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fda5-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9fda5-123">true</span><span class="sxs-lookup"><span data-stu-id="9fda5-123">true</span></span>|<span data-ttu-id="9fda5-124">Aktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly.</span><span class="sxs-lookup"><span data-stu-id="9fda5-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="9fda5-125">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="9fda5-125">This is the default.</span></span>|  
|<span data-ttu-id="9fda5-126">False</span><span class="sxs-lookup"><span data-stu-id="9fda5-126">false</span></span>|<span data-ttu-id="9fda5-127">Deaktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly.</span><span class="sxs-lookup"><span data-stu-id="9fda5-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="9fda5-128">Dadurch kann die Anwendung Verweise auf mehrere Implementierungen besitzen.</span><span class="sxs-lookup"><span data-stu-id="9fda5-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fda5-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9fda5-129">Child Elements</span></span>  
 <span data-ttu-id="9fda5-130">Keine</span><span class="sxs-lookup"><span data-stu-id="9fda5-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fda5-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9fda5-131">Parent Elements</span></span>  
  
|<span data-ttu-id="9fda5-132">Element</span><span class="sxs-lookup"><span data-stu-id="9fda5-132">Element</span></span>|<span data-ttu-id="9fda5-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fda5-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9fda5-134">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9fda5-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9fda5-135">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9fda5-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="9fda5-136">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="9fda5-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fda5-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fda5-137">Remarks</span></span>  
 <span data-ttu-id="9fda5-138">Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], wird automatisch unterstützt für Anwendungen, die beide Implementierungen von .NET Framework verwenden, können z. B. die Implementierung von .NET Framework oder .NET Framework for Silverlight-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="9fda5-138">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="9fda5-139">Die zwei Implementierungen einer bestimmten .NET Framework-Assembly werden vom Assemblybinder als äquivalent betrachtet.</span><span class="sxs-lookup"><span data-stu-id="9fda5-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="9fda5-140">In einigen Szenarien verursacht diese Anwendungsportabilitätsfunktion Probleme.</span><span class="sxs-lookup"><span data-stu-id="9fda5-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="9fda5-141">In jenen Szenarien kann das `<supportPortability>`-Element verwendet werden, um die Funktion zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9fda5-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="9fda5-142">Ein solches Szenario ist eine Assembly, die sowohl die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung einer bestimmten Verweisassembly mit Verweisen versehen muss.</span><span class="sxs-lookup"><span data-stu-id="9fda5-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="9fda5-143">Ein in Windows Presentation Foundation (WPF) geschriebener XAML-Designer müsste möglicherweise sowohl auf die WPF-Desktopimplementierung, für die Benutzeroberfläche des Designers, als auch die Teilmenge von WPF, die in der Silverlight-Implementierung enthalten ist, verweisen.</span><span class="sxs-lookup"><span data-stu-id="9fda5-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="9fda5-144">Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht.</span><span class="sxs-lookup"><span data-stu-id="9fda5-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="9fda5-145">Dieses Element deaktiviert das Standardverhalten und ermöglicht eine erfolgreiche Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="9fda5-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9fda5-146">Damit der Compiler die Informationen an die Assemblybindungs-Logik der Common Language Runtime übergibt, müssen Sie den Speicherort der Datei „app.config“, die dieses Element enthält, mithilfe der `/appconfig`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="9fda5-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fda5-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fda5-147">Example</span></span>  
 <span data-ttu-id="9fda5-148">Das folgende Beispiel ermöglicht einer Anwendung, über Verweise sowohl auf die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung jeder die oft ausgegebene Befehlszeilen  .NET Framework-Assembly, die in beiden Implementierungen vorhanden ist, zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="9fda5-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="9fda5-149">Mit der `/appconfig`-Compileroption muss der Speicherort dieser app.config-Datei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9fda5-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9fda5-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fda5-150">See also</span></span>
- [<span data-ttu-id="9fda5-151">/ appconfig (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="9fda5-151">/appconfig (C# Compiler Options)</span></span>](../../../../../docs/csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="9fda5-152">[Übersicht über die Vereinheitlichung von .NET Framework-Assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9fda5-152">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
