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
ms.openlocfilehash: 19fa1561ca3acd845918d952379c5227121465b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174068"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="514b6-102">\<requiredRuntime>-Element</span><span class="sxs-lookup"><span data-stu-id="514b6-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="514b6-103">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="514b6-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="514b6-104">Dieses Element ist veraltet und sollte nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="514b6-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="514b6-105">[`supportedRuntime`](supportedruntime-element.md)Stattdessen sollte das-Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="514b6-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a><span data-ttu-id="514b6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="514b6-106">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="514b6-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="514b6-107">Attributes and elements</span></span>

<span data-ttu-id="514b6-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="514b6-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="514b6-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="514b6-109">Attributes</span></span>

|<span data-ttu-id="514b6-110">attribute</span><span class="sxs-lookup"><span data-stu-id="514b6-110">Attribute</span></span>|<span data-ttu-id="514b6-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="514b6-111">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="514b6-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="514b6-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="514b6-113">Ein Zeichen folgen Wert, der die Version der .NET Framework angibt, die von dieser Anwendung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="514b6-113">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="514b6-114">Der Zeichen folgen Wert muss mit dem Verzeichnisnamen unter dem Stammverzeichnis der .NET Framework Installation identisch sein.</span><span class="sxs-lookup"><span data-stu-id="514b6-114">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="514b6-115">Der Inhalt des Zeichen folgen Werts wird nicht analysiert.</span><span class="sxs-lookup"><span data-stu-id="514b6-115">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="514b6-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="514b6-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="514b6-117">Gibt an, ob der Startcode der Laufzeit die Registrierung durchsucht, um die Laufzeitversion zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="514b6-117">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="514b6-118">safemode-Attribut</span><span class="sxs-lookup"><span data-stu-id="514b6-118">safemode attribute</span></span>

|<span data-ttu-id="514b6-119">Wert</span><span class="sxs-lookup"><span data-stu-id="514b6-119">Value</span></span>|<span data-ttu-id="514b6-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="514b6-120">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="514b6-121">Der Startcode der Laufzeit sucht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="514b6-121">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="514b6-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="514b6-122">This is the default value.</span></span>|
|`true`|<span data-ttu-id="514b6-123">Der Startcode der Laufzeit sucht nicht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="514b6-123">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="514b6-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="514b6-124">Child elements</span></span>

<span data-ttu-id="514b6-125">Keine</span><span class="sxs-lookup"><span data-stu-id="514b6-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="514b6-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="514b6-126">Parent elements</span></span>

|<span data-ttu-id="514b6-127">Element</span><span class="sxs-lookup"><span data-stu-id="514b6-127">Element</span></span>|<span data-ttu-id="514b6-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="514b6-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="514b6-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="514b6-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="514b6-130">Enthält das- `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="514b6-130">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="514b6-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="514b6-131">Remarks</span></span>

 <span data-ttu-id="514b6-132">Anwendungen, die zur Unterstützung von nur Version 1,0 der Laufzeit erstellt wurden, müssen das- `<requiredRuntime>` Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="514b6-132">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="514b6-133">Anwendungen, die mit Version 1,1 oder höher der Laufzeit erstellt wurden, müssen das- `<supportedRuntime>` Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="514b6-133">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="514b6-134">Wenn Sie die [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) -Funktion verwenden, um die Konfigurationsdatei anzugeben, müssen Sie das- `<requiredRuntime>` Element für alle Versionen der Common Language Runtime verwenden.</span><span class="sxs-lookup"><span data-stu-id="514b6-134">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="514b6-135">Das- `<supportedRuntime>` Element wird ignoriert, wenn Sie [corbindtoriuntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="514b6-135">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="514b6-136">Die `version` Attribut Zeichenfolge muss mit dem Namen des Installations Ordners für die angegebene Version der .NET Framework identisch sein.</span><span class="sxs-lookup"><span data-stu-id="514b6-136">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="514b6-137">Diese Zeichenfolge wird nicht interpretiert.</span><span class="sxs-lookup"><span data-stu-id="514b6-137">This string is not interpreted.</span></span> <span data-ttu-id="514b6-138">Wenn der Startcode der Laufzeit keinen übereinstimmenden Ordner findet, wird die Laufzeit nicht geladen. der Startcode zeigt eine Fehlermeldung an und beendet den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="514b6-138">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="514b6-139">Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert das- `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="514b6-139">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="514b6-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="514b6-140">Example</span></span>

<span data-ttu-id="514b6-141">Im folgenden Beispiel wird gezeigt, wie die Laufzeitversion in einer Konfigurationsdatei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="514b6-141">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="514b6-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="514b6-142">See also</span></span>

- [<span data-ttu-id="514b6-143">Schema für Start Einstellungen</span><span class="sxs-lookup"><span data-stu-id="514b6-143">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="514b6-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="514b6-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="514b6-145">How to: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="514b6-145">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
