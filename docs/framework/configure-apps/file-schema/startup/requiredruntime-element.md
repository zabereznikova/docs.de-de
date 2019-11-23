---
title: <requiredRuntime>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697490"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="41bcc-102">\<> Element "Requirements druntime"</span><span class="sxs-lookup"><span data-stu-id="41bcc-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="41bcc-103">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41bcc-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="41bcc-104">Dieses Element ist veraltet und sollte nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41bcc-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="41bcc-105">Stattdessen sollte das [`supportedRuntime`](supportedruntime-element.md) -Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41bcc-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[<span data-ttu-id="41bcc-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="41bcc-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="41bcc-107">&nbsp;&nbsp;[ **\<Start >** ](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="41bcc-107">&nbsp;&nbsp;[**\<startup>**](startup-element.md)</span></span>  
<span data-ttu-id="41bcc-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<"Requirements druntime" >**</span><span class="sxs-lookup"><span data-stu-id="41bcc-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="41bcc-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="41bcc-109">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41bcc-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="41bcc-110">Attributes and elements</span></span>

<span data-ttu-id="41bcc-111">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="41bcc-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="41bcc-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="41bcc-112">Attributes</span></span>

|<span data-ttu-id="41bcc-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="41bcc-113">Attribute</span></span>|<span data-ttu-id="41bcc-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41bcc-114">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="41bcc-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="41bcc-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="41bcc-116">Ein Zeichen folgen Wert, der die Version der .NET Framework angibt, die von dieser Anwendung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="41bcc-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="41bcc-117">Der Zeichen folgen Wert muss mit dem Verzeichnisnamen unter dem Stammverzeichnis der .NET Framework Installation identisch sein.</span><span class="sxs-lookup"><span data-stu-id="41bcc-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="41bcc-118">Der Inhalt des Zeichen folgen Werts wird nicht analysiert.</span><span class="sxs-lookup"><span data-stu-id="41bcc-118">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="41bcc-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="41bcc-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="41bcc-120">Gibt an, ob der Startcode der Laufzeit die Registrierung durchsucht, um die Laufzeitversion zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="41bcc-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="41bcc-121">safemode-Attribut</span><span class="sxs-lookup"><span data-stu-id="41bcc-121">safemode attribute</span></span>

|<span data-ttu-id="41bcc-122">Wert</span><span class="sxs-lookup"><span data-stu-id="41bcc-122">Value</span></span>|<span data-ttu-id="41bcc-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41bcc-123">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="41bcc-124">Der Startcode der Laufzeit sucht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="41bcc-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="41bcc-125">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="41bcc-125">This is the default value.</span></span>|
|`true`|<span data-ttu-id="41bcc-126">Der Startcode der Laufzeit sucht nicht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="41bcc-126">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="41bcc-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41bcc-127">Child elements</span></span>

<span data-ttu-id="41bcc-128">None.</span><span class="sxs-lookup"><span data-stu-id="41bcc-128">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="41bcc-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41bcc-129">Parent elements</span></span>

|<span data-ttu-id="41bcc-130">Element</span><span class="sxs-lookup"><span data-stu-id="41bcc-130">Element</span></span>|<span data-ttu-id="41bcc-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41bcc-131">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="41bcc-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="41bcc-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="41bcc-133">Enthält das `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="41bcc-133">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="41bcc-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41bcc-134">Remarks</span></span>
 <span data-ttu-id="41bcc-135">Anwendungen, die zur Unterstützung von nur Version 1,0 der Laufzeit erstellt wurden, müssen das `<requiredRuntime>`-Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="41bcc-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="41bcc-136">Anwendungen, die mit Version 1,1 oder höher der Laufzeit erstellt wurden, müssen das `<supportedRuntime>`-Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="41bcc-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="41bcc-137">Wenn Sie die [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) -Funktion verwenden, um die Konfigurationsdatei anzugeben, müssen Sie das `<requiredRuntime>`-Element für alle Versionen der Laufzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="41bcc-137">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="41bcc-138">Das `<supportedRuntime>`-Element wird ignoriert, wenn Sie [corbindtoriuntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="41bcc-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="41bcc-139">Die `version`-Attribut Zeichenfolge muss mit dem Namen des Installations Ordners für die angegebene Version des .NET Framework identisch sein.</span><span class="sxs-lookup"><span data-stu-id="41bcc-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="41bcc-140">Diese Zeichenfolge wird nicht interpretiert.</span><span class="sxs-lookup"><span data-stu-id="41bcc-140">This string is not interpreted.</span></span> <span data-ttu-id="41bcc-141">Wenn der Startcode der Laufzeit keinen übereinstimmenden Ordner findet, wird die Laufzeit nicht geladen. der Startcode zeigt eine Fehlermeldung an und beendet den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="41bcc-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="41bcc-142">Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert das `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="41bcc-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="41bcc-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41bcc-143">Example</span></span>

<span data-ttu-id="41bcc-144">Im folgenden Beispiel wird gezeigt, wie die Laufzeitversion in einer Konfigurationsdatei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="41bcc-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="41bcc-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41bcc-145">See also</span></span>

- [<span data-ttu-id="41bcc-146">Startup Settings Schema (Schema für Starteinstellungen)</span><span class="sxs-lookup"><span data-stu-id="41bcc-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="41bcc-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="41bcc-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="41bcc-148">Gewusst wie: Konfigurieren einer APP für die Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="41bcc-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
