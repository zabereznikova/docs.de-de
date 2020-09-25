---
title: <PreferComInsteadOfManagedRemoting>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 2fb0d94f91d28f9d9d4f247411d273f786f7b63b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195284"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="12fb2-102">\<PreferComInsteadOfManagedRemoting>-Element</span><span class="sxs-lookup"><span data-stu-id="12fb2-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>

<span data-ttu-id="12fb2-103">Gibt an, ob die Laufzeit COM-Interop anstelle von Remoting für alle Aufrufe über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="12fb2-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**  
  
## <a name="syntax"></a><span data-ttu-id="12fb2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12fb2-104">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12fb2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="12fb2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="12fb2-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12fb2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12fb2-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="12fb2-107">Attributes</span></span>  
  
|<span data-ttu-id="12fb2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="12fb2-108">Attribute</span></span>|<span data-ttu-id="12fb2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12fb2-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="12fb2-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="12fb2-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="12fb2-111">Gibt an, ob die Laufzeit COM-Interop anstelle eines Remoting über Anwendungs Domänen Grenzen hinweg verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="12fb2-111">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="12fb2-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="12fb2-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="12fb2-113">Wert</span><span class="sxs-lookup"><span data-stu-id="12fb2-113">Value</span></span>|<span data-ttu-id="12fb2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12fb2-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="12fb2-115">Die Laufzeit verwendet Remoting über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="12fb2-115">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="12fb2-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="12fb2-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="12fb2-117">Die Laufzeit verwendet COM-Interop über Anwendungs Domänen Grenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="12fb2-117">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12fb2-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12fb2-118">Child Elements</span></span>  

 <span data-ttu-id="12fb2-119">Keine</span><span class="sxs-lookup"><span data-stu-id="12fb2-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12fb2-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12fb2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="12fb2-121">Element</span><span class="sxs-lookup"><span data-stu-id="12fb2-121">Element</span></span>|<span data-ttu-id="12fb2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12fb2-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="12fb2-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="12fb2-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="12fb2-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="12fb2-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12fb2-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="12fb2-125">Remarks</span></span>  

 <span data-ttu-id="12fb2-126">Wenn Sie das- `enabled` Attribut auf festlegen `true` , verhält sich die Laufzeit wie folgt:</span><span class="sxs-lookup"><span data-stu-id="12fb2-126">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="12fb2-127">Die Laufzeit ruft [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle nicht auf, wenn eine [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) -Schnittstelle über eine COM-Schnittstelle in die Domäne gelangt.</span><span class="sxs-lookup"><span data-stu-id="12fb2-127">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="12fb2-128">Stattdessen wird ein [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) um das Objekt konstruiert.</span><span class="sxs-lookup"><span data-stu-id="12fb2-128">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="12fb2-129">Die Laufzeit gibt E_NOINTERFACE zurück, wenn Sie einen `QueryInterface` Aufruf für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle für einen [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) empfängt, der in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="12fb2-129">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="12fb2-130">Diese beiden Verhalten stellen sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Anwendungs Domänen Grenzen hinweg com und COM-Interop anstelle von Remoting verwenden.</span><span class="sxs-lookup"><span data-stu-id="12fb2-130">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12fb2-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12fb2-131">Example</span></span>  

 <span data-ttu-id="12fb2-132">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Common Language Runtime COM-Interop über Isolations Grenzen hinweg verwenden soll:</span><span class="sxs-lookup"><span data-stu-id="12fb2-132">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="12fb2-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12fb2-133">See also</span></span>

- [<span data-ttu-id="12fb2-134">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="12fb2-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="12fb2-135">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="12fb2-135">Configuration File Schema</span></span>](../index.md)
