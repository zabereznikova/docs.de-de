---
title: <PreferComInsteadOfManagedRemoting>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 1376df4efd56734f2b8da9bd76033afcce8a285b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452252"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="00a22-102">\<prefercominsteadof managedremoting > Element</span><span class="sxs-lookup"><span data-stu-id="00a22-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="00a22-103">Gibt an, ob die Laufzeit COM-Interop anstelle von Remoting für alle Aufrufe über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="00a22-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="00a22-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00a22-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00a22-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="00a22-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="00a22-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<prefercominsteadof managedremoting >**</span><span class="sxs-lookup"><span data-stu-id="00a22-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a22-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="00a22-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00a22-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00a22-108">Attributes and Elements</span></span>  
 <span data-ttu-id="00a22-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00a22-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00a22-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="00a22-110">Attributes</span></span>  
  
|<span data-ttu-id="00a22-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="00a22-111">Attribute</span></span>|<span data-ttu-id="00a22-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00a22-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="00a22-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="00a22-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="00a22-114">Gibt an, ob die Laufzeit COM-Interop anstelle eines Remoting über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="00a22-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="00a22-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="00a22-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="00a22-116">Wert</span><span class="sxs-lookup"><span data-stu-id="00a22-116">Value</span></span>|<span data-ttu-id="00a22-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00a22-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="00a22-118">Die Laufzeit verwendet Remoting über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="00a22-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="00a22-119">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="00a22-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="00a22-120">Die Laufzeit verwendet COM-Interop über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="00a22-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00a22-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00a22-121">Child Elements</span></span>  
 <span data-ttu-id="00a22-122">None.</span><span class="sxs-lookup"><span data-stu-id="00a22-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00a22-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00a22-123">Parent Elements</span></span>  
  
|<span data-ttu-id="00a22-124">Element</span><span class="sxs-lookup"><span data-stu-id="00a22-124">Element</span></span>|<span data-ttu-id="00a22-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00a22-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="00a22-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="00a22-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="00a22-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="00a22-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00a22-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00a22-128">Remarks</span></span>  
 <span data-ttu-id="00a22-129">Wenn Sie das `enabled`-Attribut auf `true`festlegen, verhält sich die Laufzeit wie folgt:</span><span class="sxs-lookup"><span data-stu-id="00a22-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="00a22-130">Die Laufzeit ruft [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle nicht auf, wenn eine [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) -Schnittstelle über eine COM-Schnittstelle in die Domäne gelangt.</span><span class="sxs-lookup"><span data-stu-id="00a22-130">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="00a22-131">Stattdessen wird ein [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) um das Objekt konstruiert.</span><span class="sxs-lookup"><span data-stu-id="00a22-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="00a22-132">Die Laufzeit gibt E_NOINTERFACE zurück, wenn Sie einen `QueryInterface` Aufruf einer [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle für einen [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) empfängt, der in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="00a22-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="00a22-133">Diese beiden Verhalten stellen sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Anwendungs Domänen Grenzen hinweg com und COM-Interop anstelle von Remoting verwenden.</span><span class="sxs-lookup"><span data-stu-id="00a22-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00a22-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00a22-134">Example</span></span>  
 <span data-ttu-id="00a22-135">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Common Language Runtime COM-Interop über Isolations Grenzen hinweg verwenden soll:</span><span class="sxs-lookup"><span data-stu-id="00a22-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00a22-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00a22-136">See also</span></span>

- [<span data-ttu-id="00a22-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="00a22-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="00a22-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="00a22-138">Configuration File Schema</span></span>](../index.md)
