---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c05e27226a58086c806e8977ba50a55873d1167e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43798181"
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="dddca-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span><span class="sxs-lookup"><span data-stu-id="dddca-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="dddca-103">Gibt an, ob die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting für alle Aufrufe über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dddca-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="dddca-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dddca-104">\<configuration></span></span>  
<span data-ttu-id="dddca-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="dddca-105">\<runtime></span></span>  
<span data-ttu-id="dddca-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="dddca-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dddca-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="dddca-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dddca-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dddca-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dddca-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dddca-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dddca-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="dddca-110">Attributes</span></span>  
  
|<span data-ttu-id="dddca-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="dddca-111">Attribute</span></span>|<span data-ttu-id="dddca-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dddca-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="dddca-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="dddca-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="dddca-114">Gibt an, ob die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting über Anwendungsdomänen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dddca-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="dddca-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="dddca-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="dddca-116">Wert</span><span class="sxs-lookup"><span data-stu-id="dddca-116">Value</span></span>|<span data-ttu-id="dddca-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dddca-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="dddca-118">Die Laufzeit wird Remoting über Anwendungsdomänen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dddca-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="dddca-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="dddca-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="dddca-120">Die Runtime wird COM-Interop über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dddca-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dddca-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dddca-121">Child Elements</span></span>  
 <span data-ttu-id="dddca-122">Keine</span><span class="sxs-lookup"><span data-stu-id="dddca-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dddca-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dddca-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dddca-124">Element</span><span class="sxs-lookup"><span data-stu-id="dddca-124">Element</span></span>|<span data-ttu-id="dddca-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dddca-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dddca-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dddca-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dddca-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="dddca-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dddca-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dddca-128">Remarks</span></span>  
 <span data-ttu-id="dddca-129">Beim Festlegen der `enabled` Attribut `true`, die Laufzeit verhält sich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dddca-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="dddca-130">Die Runtime ruft nicht [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle, wenn ein [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) Schnittstelle gibt die Domäne über eine COM-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dddca-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="dddca-131">Stattdessen erstellt eine [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="dddca-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="dddca-132">Die Laufzeit wird E_NOINTERFACE zurückgegeben, wenn er empfängt eine `QueryInterface` rufen Sie für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle für alle [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW), die in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dddca-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="dddca-133">Diese zwei Verhaltensweisen stellen Sie sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Domänen hinweg Anwendungsverwendung COM- und COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting.</span><span class="sxs-lookup"><span data-stu-id="dddca-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dddca-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dddca-134">Example</span></span>  
 <span data-ttu-id="dddca-135">Das folgende Beispiel zeigt wie angegeben, dass die Runtime COM verwenden soll, die über Isolationsgrenzen hinweg interop:</span><span class="sxs-lookup"><span data-stu-id="dddca-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dddca-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dddca-136">See Also</span></span>  
 [<span data-ttu-id="dddca-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="dddca-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="dddca-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="dddca-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
