---
title: <PreferComInsteadOfManagedRemoting>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c7a558af17493c955b4f148d0abf7f42c9dd6f8
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629434"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="c3e48-102">\<Prefercominsteadof managedremoting-> Element</span><span class="sxs-lookup"><span data-stu-id="c3e48-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="c3e48-103">Gibt an, ob die Laufzeit COM-Interop anstelle von Remoting für alle Aufrufe über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="c3e48-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="c3e48-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c3e48-104">\<configuration></span></span>  
<span data-ttu-id="c3e48-105">\<Lauf Zeit ></span><span class="sxs-lookup"><span data-stu-id="c3e48-105">\<runtime></span></span>  
<span data-ttu-id="c3e48-106">\<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="c3e48-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3e48-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3e48-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3e48-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c3e48-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c3e48-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c3e48-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3e48-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3e48-110">Attributes</span></span>  
  
|<span data-ttu-id="c3e48-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="c3e48-111">Attribute</span></span>|<span data-ttu-id="c3e48-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3e48-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c3e48-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c3e48-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c3e48-114">Gibt an, ob die Laufzeit COM-Interop anstelle eines Remoting über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="c3e48-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c3e48-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="c3e48-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c3e48-116">Wert</span><span class="sxs-lookup"><span data-stu-id="c3e48-116">Value</span></span>|<span data-ttu-id="c3e48-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3e48-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c3e48-118">Die Laufzeit verwendet Remoting über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="c3e48-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="c3e48-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="c3e48-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c3e48-120">Die Laufzeit verwendet COM-Interop über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="c3e48-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3e48-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3e48-121">Child Elements</span></span>  
 <span data-ttu-id="c3e48-122">Keine</span><span class="sxs-lookup"><span data-stu-id="c3e48-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3e48-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3e48-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c3e48-124">Element</span><span class="sxs-lookup"><span data-stu-id="c3e48-124">Element</span></span>|<span data-ttu-id="c3e48-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3e48-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c3e48-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c3e48-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c3e48-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c3e48-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3e48-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3e48-128">Remarks</span></span>  
 <span data-ttu-id="c3e48-129">Wenn Sie das `enabled` -Attribut auf `true`festlegen, verhält sich die Laufzeit wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c3e48-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="c3e48-130">Die Laufzeit ruft [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle nicht auf, wenn eine [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) -Schnittstelle über eine COM-Schnittstelle in die Domäne gelangt.</span><span class="sxs-lookup"><span data-stu-id="c3e48-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="c3e48-131">Stattdessen wird ein [Runtime Callable Wrapper](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) um das Objekt konstruiert.</span><span class="sxs-lookup"><span data-stu-id="c3e48-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="c3e48-132">Die Laufzeit gibt E_NOINTERFACE zurück, wenn Sie `QueryInterface` einen Aufruf für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle für einen [COM Callable Wrapper](../../../../../docs/standard/native-interop/com-callable-wrapper.md) (CCW) empfängt, der in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c3e48-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="c3e48-133">Diese beiden Verhalten stellen sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Anwendungs Domänen Grenzen hinweg com und COM-Interop anstelle von Remoting verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3e48-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3e48-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3e48-134">Example</span></span>  
 <span data-ttu-id="c3e48-135">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Common Language Runtime COM-Interop über Isolations Grenzen hinweg verwenden soll:</span><span class="sxs-lookup"><span data-stu-id="c3e48-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3e48-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3e48-136">See also</span></span>

- [<span data-ttu-id="c3e48-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c3e48-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="c3e48-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="c3e48-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
