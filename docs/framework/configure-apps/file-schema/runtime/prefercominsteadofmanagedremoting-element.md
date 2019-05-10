---
title: <PreferComInsteadOfManagedRemoting>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32e4b490f0824cf97a1ae5910d7c74801c7b439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592692"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="07c78-102">\<PreferComInsteadOfManagedRemoting >-Element</span><span class="sxs-lookup"><span data-stu-id="07c78-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="07c78-103">Gibt an, ob die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting für alle Aufrufe über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07c78-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="07c78-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="07c78-104">\<configuration></span></span>  
<span data-ttu-id="07c78-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="07c78-105">\<runtime></span></span>  
<span data-ttu-id="07c78-106">\<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="07c78-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07c78-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="07c78-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07c78-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07c78-108">Attributes and Elements</span></span>  
 <span data-ttu-id="07c78-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07c78-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07c78-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="07c78-110">Attributes</span></span>  
  
|<span data-ttu-id="07c78-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="07c78-111">Attribute</span></span>|<span data-ttu-id="07c78-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07c78-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="07c78-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="07c78-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="07c78-114">Gibt an, ob die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting über Anwendungsdomänen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07c78-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="07c78-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="07c78-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="07c78-116">Wert</span><span class="sxs-lookup"><span data-stu-id="07c78-116">Value</span></span>|<span data-ttu-id="07c78-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07c78-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="07c78-118">Die Laufzeit wird Remoting über Anwendungsdomänen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07c78-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="07c78-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="07c78-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="07c78-120">Die Runtime wird COM-Interop über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07c78-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07c78-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07c78-121">Child Elements</span></span>  
 <span data-ttu-id="07c78-122">Keine</span><span class="sxs-lookup"><span data-stu-id="07c78-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07c78-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07c78-123">Parent Elements</span></span>  
  
|<span data-ttu-id="07c78-124">Element</span><span class="sxs-lookup"><span data-stu-id="07c78-124">Element</span></span>|<span data-ttu-id="07c78-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07c78-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="07c78-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="07c78-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="07c78-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="07c78-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07c78-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07c78-128">Remarks</span></span>  
 <span data-ttu-id="07c78-129">Beim Festlegen der `enabled` Attribut `true`, die Laufzeit verhält sich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="07c78-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="07c78-130">Die Runtime ruft nicht [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle, wenn ein [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) Schnittstelle gibt die Domäne über eine COM-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="07c78-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="07c78-131">Stattdessen erstellt eine [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="07c78-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="07c78-132">Die Laufzeit wird E_NOINTERFACE zurückgegeben, wenn er empfängt eine `QueryInterface` rufen Sie für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle für alle [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW), die in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="07c78-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="07c78-133">Diese zwei Verhaltensweisen stellen Sie sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Domänen hinweg Anwendungsverwendung COM- und COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting.</span><span class="sxs-lookup"><span data-stu-id="07c78-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07c78-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07c78-134">Example</span></span>  
 <span data-ttu-id="07c78-135">Das folgende Beispiel zeigt wie angegeben, dass die Runtime COM verwenden soll, die über Isolationsgrenzen hinweg interop:</span><span class="sxs-lookup"><span data-stu-id="07c78-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="07c78-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07c78-136">See also</span></span>

- [<span data-ttu-id="07c78-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="07c78-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="07c78-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="07c78-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
