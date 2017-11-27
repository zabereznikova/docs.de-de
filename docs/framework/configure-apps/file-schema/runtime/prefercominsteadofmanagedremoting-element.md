---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7aed6baa227b2bdf90c26f02d38ee67c1ffbbda1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="6eba5-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span><span class="sxs-lookup"><span data-stu-id="6eba5-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="6eba5-103">Gibt an, ob die Laufzeit COM-Interop anstelle von Remoting für alle Aufrufe über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6eba5-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="6eba5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6eba5-104">\<configuration></span></span>  
<span data-ttu-id="6eba5-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="6eba5-105">\<runtime></span></span>  
<span data-ttu-id="6eba5-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="6eba5-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eba5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6eba5-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6eba5-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6eba5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6eba5-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6eba5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6eba5-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6eba5-110">Attributes</span></span>  
  
|<span data-ttu-id="6eba5-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6eba5-111">Attribute</span></span>|<span data-ttu-id="6eba5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6eba5-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6eba5-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6eba5-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6eba5-114">Gibt an, ob die Common Language Runtime, COM-Interop anstelle von Remoting über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6eba5-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6eba5-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="6eba5-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6eba5-116">Wert</span><span class="sxs-lookup"><span data-stu-id="6eba5-116">Value</span></span>|<span data-ttu-id="6eba5-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6eba5-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6eba5-118">Die Common Language Runtime wird Remoting über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6eba5-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="6eba5-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="6eba5-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="6eba5-120">Die Common Language Runtime wird COM-Interop über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6eba5-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6eba5-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6eba5-121">Child Elements</span></span>  
 <span data-ttu-id="6eba5-122">Keine</span><span class="sxs-lookup"><span data-stu-id="6eba5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6eba5-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6eba5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6eba5-124">Element</span><span class="sxs-lookup"><span data-stu-id="6eba5-124">Element</span></span>|<span data-ttu-id="6eba5-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6eba5-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6eba5-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6eba5-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6eba5-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6eba5-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eba5-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6eba5-128">Remarks</span></span>  
 <span data-ttu-id="6eba5-129">Beim Festlegen der `enabled` -Attribut `true`, die Common Language Runtime verhält sich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6eba5-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="6eba5-130">Die Common Language Runtime nicht aufgerufen [IUnknown:: QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle, wenn ein [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) Schnittstelle wechselt in die Domäne über eine COM-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6eba5-130">The runtime does not call [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="6eba5-131">Stattdessen erstellt er eine [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) um das Objekt.</span><span class="sxs-lookup"><span data-stu-id="6eba5-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="6eba5-132">Die Common Language Runtime wird E_NOINTERFACE zurückgegeben, bei Erhalt des eine `QueryInterface` rufen Sie für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle für eine beliebige [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW), die in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6eba5-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="6eba5-133">Diese zwei Verhaltensweisen stellen Sie sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Anwendung Domäne Grenzen verwenden COM- und COM-Interop anstelle von Remoting.</span><span class="sxs-lookup"><span data-stu-id="6eba5-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6eba5-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6eba5-134">Example</span></span>  
 <span data-ttu-id="6eba5-135">Im folgende Beispiel veranschaulicht angeben, dass die Common Language Runtime für COM-Interop-hinweg Isolation:</span><span class="sxs-lookup"><span data-stu-id="6eba5-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6eba5-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eba5-136">See Also</span></span>  
 [<span data-ttu-id="6eba5-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="6eba5-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="6eba5-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="6eba5-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
