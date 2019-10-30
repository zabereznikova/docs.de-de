---
title: <PreferComInsteadOfManagedRemoting>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 47c568a8d6e89a195414552b3db5953ee61d1e55
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116015"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="4426b-102">\<prefercominsteadof managedremoting > Element</span><span class="sxs-lookup"><span data-stu-id="4426b-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="4426b-103">Gibt an, ob die Laufzeit COM-Interop anstelle von Remoting für alle Aufrufe über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="4426b-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="4426b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4426b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4426b-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="4426b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="4426b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<prefercominsteadof managedremoting >**</span><span class="sxs-lookup"><span data-stu-id="4426b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4426b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4426b-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4426b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4426b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4426b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4426b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4426b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4426b-110">Attributes</span></span>  
  
|<span data-ttu-id="4426b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4426b-111">Attribute</span></span>|<span data-ttu-id="4426b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4426b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4426b-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4426b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4426b-114">Gibt an, ob die Laufzeit COM-Interop anstelle eines Remoting über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="4426b-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4426b-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="4426b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4426b-116">Wert</span><span class="sxs-lookup"><span data-stu-id="4426b-116">Value</span></span>|<span data-ttu-id="4426b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4426b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4426b-118">Die Laufzeit verwendet Remoting über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="4426b-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="4426b-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="4426b-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4426b-120">Die Laufzeit verwendet COM-Interop über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="4426b-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4426b-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4426b-121">Child Elements</span></span>  
 <span data-ttu-id="4426b-122">Keine</span><span class="sxs-lookup"><span data-stu-id="4426b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4426b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4426b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4426b-124">Element</span><span class="sxs-lookup"><span data-stu-id="4426b-124">Element</span></span>|<span data-ttu-id="4426b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4426b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4426b-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4426b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4426b-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4426b-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4426b-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4426b-128">Remarks</span></span>  
 <span data-ttu-id="4426b-129">Wenn Sie das `enabled`-Attribut auf `true`festlegen, verhält sich die Laufzeit wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4426b-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="4426b-130">Die Laufzeit ruft [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle nicht auf, wenn eine [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) -Schnittstelle über eine COM-Schnittstelle in die Domäne gelangt.</span><span class="sxs-lookup"><span data-stu-id="4426b-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="4426b-131">Stattdessen wird ein [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) um das Objekt konstruiert.</span><span class="sxs-lookup"><span data-stu-id="4426b-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="4426b-132">Die Laufzeit gibt E_NOINTERFACE zurück, wenn Sie einen `QueryInterface` Aufruf für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle für einen [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) empfängt, der in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4426b-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="4426b-133">Diese beiden Verhalten stellen sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Anwendungs Domänen Grenzen hinweg com und COM-Interop anstelle von Remoting verwenden.</span><span class="sxs-lookup"><span data-stu-id="4426b-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4426b-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4426b-134">Example</span></span>  
 <span data-ttu-id="4426b-135">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Common Language Runtime COM-Interop über Isolations Grenzen hinweg verwenden soll:</span><span class="sxs-lookup"><span data-stu-id="4426b-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4426b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4426b-136">See also</span></span>

- [<span data-ttu-id="4426b-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="4426b-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4426b-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="4426b-138">Configuration File Schema</span></span>](../index.md)
