---
title: <PreferComInsteadOfManagedRemoting>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d793c8d84a15f554ada78f3c0dd1f0e936893fd4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252411"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="34a70-102">\<Prefercominsteadof managedremoting-> Element</span><span class="sxs-lookup"><span data-stu-id="34a70-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="34a70-103">Gibt an, ob die Laufzeit COM-Interop anstelle von Remoting für alle Aufrufe über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="34a70-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="34a70-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34a70-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34a70-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="34a70-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="34a70-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting>**</span><span class="sxs-lookup"><span data-stu-id="34a70-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a70-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="34a70-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34a70-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34a70-108">Attributes and Elements</span></span>  
 <span data-ttu-id="34a70-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34a70-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34a70-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="34a70-110">Attributes</span></span>  
  
|<span data-ttu-id="34a70-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="34a70-111">Attribute</span></span>|<span data-ttu-id="34a70-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34a70-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="34a70-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="34a70-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="34a70-114">Gibt an, ob die Laufzeit COM-Interop anstelle eines Remoting über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="34a70-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="34a70-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="34a70-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="34a70-116">Wert</span><span class="sxs-lookup"><span data-stu-id="34a70-116">Value</span></span>|<span data-ttu-id="34a70-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34a70-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="34a70-118">Die Laufzeit verwendet Remoting über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="34a70-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="34a70-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="34a70-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="34a70-120">Die Laufzeit verwendet COM-Interop über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="34a70-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34a70-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34a70-121">Child Elements</span></span>  
 <span data-ttu-id="34a70-122">Keine</span><span class="sxs-lookup"><span data-stu-id="34a70-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34a70-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34a70-123">Parent Elements</span></span>  
  
|<span data-ttu-id="34a70-124">Element</span><span class="sxs-lookup"><span data-stu-id="34a70-124">Element</span></span>|<span data-ttu-id="34a70-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34a70-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34a70-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="34a70-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="34a70-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="34a70-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34a70-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34a70-128">Remarks</span></span>  
 <span data-ttu-id="34a70-129">Wenn Sie das `enabled` -Attribut auf `true`festlegen, verhält sich die Laufzeit wie folgt:</span><span class="sxs-lookup"><span data-stu-id="34a70-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="34a70-130">Die Laufzeit ruft [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle nicht auf, wenn eine [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) -Schnittstelle über eine COM-Schnittstelle in die Domäne gelangt.</span><span class="sxs-lookup"><span data-stu-id="34a70-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="34a70-131">Stattdessen wird ein [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) um das Objekt konstruiert.</span><span class="sxs-lookup"><span data-stu-id="34a70-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="34a70-132">Die Laufzeit gibt E_NOINTERFACE zurück, wenn Sie `QueryInterface` einen Aufruf für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle für einen [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) empfängt, der in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="34a70-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="34a70-133">Diese beiden Verhalten stellen sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Anwendungs Domänen Grenzen hinweg com und COM-Interop anstelle von Remoting verwenden.</span><span class="sxs-lookup"><span data-stu-id="34a70-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a70-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34a70-134">Example</span></span>  
 <span data-ttu-id="34a70-135">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Common Language Runtime COM-Interop über Isolations Grenzen hinweg verwenden soll:</span><span class="sxs-lookup"><span data-stu-id="34a70-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34a70-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34a70-136">See also</span></span>

- [<span data-ttu-id="34a70-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="34a70-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="34a70-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="34a70-138">Configuration File Schema</span></span>](../index.md)
