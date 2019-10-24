---
title: <supportPortability>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a76c378038a19d3edb9fe0c5e61012cc854c1b7
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773928"
---
# <a name="supportportability-element"></a><span data-ttu-id="acfad-102">\<supportPortability >-Element</span><span class="sxs-lookup"><span data-stu-id="acfad-102">\<supportPortability> Element</span></span>
<span data-ttu-id="acfad-103">Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="acfad-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
<span data-ttu-id="acfad-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="acfad-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="acfad-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="acfad-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="acfad-106">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding**](assemblybinding-element-for-runtime.md) > </span><span class="sxs-lookup"><span data-stu-id="acfad-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="acfad-107">&nbsp; &nbsp; &nbsp; &nbsp; **&nbsp; &nbsp; \<supportPortability >**</span><span class="sxs-lookup"><span data-stu-id="acfad-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acfad-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="acfad-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acfad-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="acfad-109">Attributes and Elements</span></span>  

<span data-ttu-id="acfad-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="acfad-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acfad-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="acfad-111">Attributes</span></span>  
  
|<span data-ttu-id="acfad-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="acfad-112">Attribute</span></span>|<span data-ttu-id="acfad-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acfad-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acfad-114">PKT</span><span class="sxs-lookup"><span data-stu-id="acfad-114">PKT</span></span>|<span data-ttu-id="acfad-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="acfad-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="acfad-116">Gibt das öffentliche Schlüsseltoken der betreffenden Assembly als Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="acfad-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="acfad-117">enabled</span><span class="sxs-lookup"><span data-stu-id="acfad-117">enabled</span></span>|<span data-ttu-id="acfad-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="acfad-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="acfad-119">Gibt an, ob Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="acfad-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="acfad-120">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="acfad-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="acfad-121">Wert</span><span class="sxs-lookup"><span data-stu-id="acfad-121">Value</span></span>|<span data-ttu-id="acfad-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acfad-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acfad-123">true</span><span class="sxs-lookup"><span data-stu-id="acfad-123">true</span></span>|<span data-ttu-id="acfad-124">Aktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly.</span><span class="sxs-lookup"><span data-stu-id="acfad-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="acfad-125">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="acfad-125">This is the default.</span></span>|  
|<span data-ttu-id="acfad-126">False</span><span class="sxs-lookup"><span data-stu-id="acfad-126">false</span></span>|<span data-ttu-id="acfad-127">Deaktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly.</span><span class="sxs-lookup"><span data-stu-id="acfad-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="acfad-128">Dadurch kann die Anwendung Verweise auf mehrere Implementierungen besitzen.</span><span class="sxs-lookup"><span data-stu-id="acfad-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acfad-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acfad-129">Child Elements</span></span>  

<span data-ttu-id="acfad-130">Keine</span><span class="sxs-lookup"><span data-stu-id="acfad-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acfad-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acfad-131">Parent Elements</span></span>  
  
|<span data-ttu-id="acfad-132">Element</span><span class="sxs-lookup"><span data-stu-id="acfad-132">Element</span></span>|<span data-ttu-id="acfad-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acfad-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="acfad-134">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="acfad-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="acfad-135">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="acfad-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="acfad-136">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="acfad-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acfad-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="acfad-137">Remarks</span></span>  

<span data-ttu-id="acfad-138">Ab .NET Framework 4 wird die Unterstützung für Anwendungen automatisch bereitgestellt, die eine der beiden Implementierungen der .NET Framework verwenden können, z. b. entweder die .NET Framework-Implementierung oder die .NET Framework für die Silverlight-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="acfad-138">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="acfad-139">Die zwei Implementierungen einer bestimmten .NET Framework-Assembly werden vom Assemblybinder als äquivalent betrachtet.</span><span class="sxs-lookup"><span data-stu-id="acfad-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="acfad-140">In einigen Szenarien verursacht diese Anwendungsportabilitätsfunktion Probleme.</span><span class="sxs-lookup"><span data-stu-id="acfad-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="acfad-141">In jenen Szenarien kann das `<supportPortability>`-Element verwendet werden, um die Funktion zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="acfad-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
<span data-ttu-id="acfad-142">Ein solches Szenario ist eine Assembly, die sowohl die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung einer bestimmten Verweisassembly mit Verweisen versehen muss.</span><span class="sxs-lookup"><span data-stu-id="acfad-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="acfad-143">Ein in Windows Presentation Foundation (WPF) geschriebener XAML-Designer müsste möglicherweise sowohl auf die WPF-Desktopimplementierung, für die Benutzeroberfläche des Designers, als auch die Teilmenge von WPF, die in der Silverlight-Implementierung enthalten ist, verweisen.</span><span class="sxs-lookup"><span data-stu-id="acfad-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="acfad-144">Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht.</span><span class="sxs-lookup"><span data-stu-id="acfad-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="acfad-145">Dieses Element deaktiviert das Standardverhalten und ermöglicht eine erfolgreiche Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="acfad-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="acfad-146">Damit der Compiler die Informationen an die Assemblybindungs-Logik der Common Language Runtime übergibt, müssen Sie den Speicherort der Datei „app.config“, die dieses Element enthält, mithilfe der `/appconfig`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="acfad-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acfad-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="acfad-147">Example</span></span>  

<span data-ttu-id="acfad-148">Das folgende Beispiel ermöglicht einer Anwendung, über Verweise sowohl auf die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung jeder die oft ausgegebene Befehlszeilen  .NET Framework-Assembly, die in beiden Implementierungen vorhanden ist, zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="acfad-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="acfad-149">Mit der `/appconfig`-Compileroption muss der Speicherort dieser app.config-Datei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="acfad-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="acfad-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acfad-150">See also</span></span>

- [<span data-ttu-id="acfad-151">-appconfig (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="acfad-151">-appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="acfad-152">[Übersicht über .NET Framework Assemblyvereinheitlichung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="acfad-152">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
