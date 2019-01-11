---
title: '&lt;RequiredRuntime&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 66de3e30ce862cd317e80ea267bf22ce728aca82
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222128"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="70d21-102">&lt;RequiredRuntime&gt; Element</span><span class="sxs-lookup"><span data-stu-id="70d21-102">&lt;requiredRuntime&gt; element</span></span>

<span data-ttu-id="70d21-103">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="70d21-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="70d21-104">Dieses Element ist veraltet und sollte nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70d21-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="70d21-105">Die [ `supportedRuntime` ](supportedruntime-element.md) Element sollte stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70d21-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

<span data-ttu-id="70d21-106">\<Konfiguration > \<Start > \<RequiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="70d21-106">\<configuration> \<startup> \<requiredRuntime></span></span>

## <a name="syntax"></a><span data-ttu-id="70d21-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="70d21-107">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="70d21-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="70d21-108">Attributes and elements</span></span>

<span data-ttu-id="70d21-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="70d21-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="70d21-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="70d21-110">Attributes</span></span>

|<span data-ttu-id="70d21-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="70d21-111">Attribute</span></span>|<span data-ttu-id="70d21-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70d21-112">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="70d21-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="70d21-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="70d21-114">Ein Zeichenfolgenwert, der angibt, die Version von .NET Framework, die diese Anwendung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="70d21-114">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="70d21-115">Der Zeichenfolgenwert muss den Namen des Verzeichnisses finden Sie unter dem Stamm der .NET Framework-Installation übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="70d21-115">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="70d21-116">Der Inhalt des Zeichenfolgenwerts wird nicht analysiert.</span><span class="sxs-lookup"><span data-stu-id="70d21-116">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="70d21-117">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="70d21-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="70d21-118">Gibt an, ob die Common Language Runtime-Startcode die Registrierung zum Ermitteln der RuntimeVersion der Common Language durchsucht.</span><span class="sxs-lookup"><span data-stu-id="70d21-118">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="70d21-119">Safemode-Attribut</span><span class="sxs-lookup"><span data-stu-id="70d21-119">safemode attribute</span></span>

|<span data-ttu-id="70d21-120">Wert</span><span class="sxs-lookup"><span data-stu-id="70d21-120">Value</span></span>|<span data-ttu-id="70d21-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70d21-121">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="70d21-122">Der Startcode für die Common Language Runtime sucht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="70d21-122">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="70d21-123">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="70d21-123">This is the default value.</span></span>|
|`true`|<span data-ttu-id="70d21-124">Der Laufzeitstartcode scheint sich nicht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="70d21-124">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="70d21-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70d21-125">Child elements</span></span>

<span data-ttu-id="70d21-126">Keine</span><span class="sxs-lookup"><span data-stu-id="70d21-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="70d21-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70d21-127">Parent elements</span></span>

|<span data-ttu-id="70d21-128">Element</span><span class="sxs-lookup"><span data-stu-id="70d21-128">Element</span></span>|<span data-ttu-id="70d21-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70d21-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="70d21-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="70d21-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="70d21-131">Enthält die `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="70d21-131">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="70d21-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70d21-132">Remarks</span></span>
 <span data-ttu-id="70d21-133">Anwendungen, die nur in Version 1.0 von der Laufzeit nicht verwenden, müssen die `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="70d21-133">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="70d21-134">Erstellen von Anwendungen mit Version 1.1 oder höher der Runtime verwenden, müssen die `<supportedRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="70d21-134">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="70d21-135">Bei Verwendung der [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) Funktion, um die Konfigurationsdatei angeben, müssen Sie die `<requiredRuntime>` -Element für alle Versionen der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="70d21-135">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="70d21-136">Die `<supportedRuntime>` Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="70d21-136">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="70d21-137">Die `version` Attributzeichenfolge muss den Ordnernamen Installation, für die angegebene Version von .NET Framework entsprechen.</span><span class="sxs-lookup"><span data-stu-id="70d21-137">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="70d21-138">Diese Zeichenfolge wird nicht interpretiert.</span><span class="sxs-lookup"><span data-stu-id="70d21-138">This string is not interpreted.</span></span> <span data-ttu-id="70d21-139">Wenn der Laufzeitstartcode einen entsprechenden Ordner nicht gefunden wird, ist die Runtime nicht geladen werden. der Startcode zeigt eine Fehlermeldung an und wird beendet.</span><span class="sxs-lookup"><span data-stu-id="70d21-139">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="70d21-140">Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert der `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="70d21-140">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="70d21-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70d21-141">Example</span></span>

<span data-ttu-id="70d21-142">Das folgende Beispiel zeigt, wie die Runtime-Version in einer Konfigurationsdatei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="70d21-142">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="70d21-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70d21-143">See also</span></span>

- [<span data-ttu-id="70d21-144">Startup Settings Schema (Schema für Starteinstellungen)</span><span class="sxs-lookup"><span data-stu-id="70d21-144">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="70d21-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="70d21-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="70d21-146">Vorgehensweise: Konfigurieren einer app zur Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="70d21-146">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)