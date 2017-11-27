---
title: '&lt;EnforceFIPSPolicy&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9bd593c17d752b35919985aad37f675c62e6ce34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="01404-102">&lt;EnforceFIPSPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="01404-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="01404-103">Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.</span><span class="sxs-lookup"><span data-stu-id="01404-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="01404-104">\<Konfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="01404-104">\<configuration> Element</span></span>  
<span data-ttu-id="01404-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="01404-105">\<runtime> Element</span></span>  
<span data-ttu-id="01404-106">\<EnforceFIPSPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="01404-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01404-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="01404-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01404-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="01404-108">Attributes and Elements</span></span>  
 <span data-ttu-id="01404-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="01404-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01404-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="01404-110">Attributes</span></span>  
  
|<span data-ttu-id="01404-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="01404-111">Attribute</span></span>|<span data-ttu-id="01404-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01404-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01404-113">enabled</span><span class="sxs-lookup"><span data-stu-id="01404-113">enabled</span></span>|<span data-ttu-id="01404-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="01404-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="01404-115">Gibt an, ob die Erzwingung von einem Computer erforderlich, dass kryptografische Algorithmen mit FIPS kompatibel sein müssen.</span><span class="sxs-lookup"><span data-stu-id="01404-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="01404-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="01404-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="01404-117">Wert</span><span class="sxs-lookup"><span data-stu-id="01404-117">Value</span></span>|<span data-ttu-id="01404-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01404-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="01404-119">Wenn Ihr Computer konfiguriert ist, um kryptografische Algorithmen FIPS-konform sein müssen, wird diese Anforderung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="01404-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="01404-120">Wenn eine Klasse einen Algorithmus implementiert, der nicht mit FIPS, die Konstruktoren kompatibel ist oder `Create` Methoden für diese Klasse Ausnahmen auslösen, wenn sie auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="01404-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="01404-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="01404-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="01404-122">Kryptografische Algorithmen, die von der Anwendung verwendet werden sind nicht kompatibel mit FIPS, unabhängig von der Konfiguration des Computers ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="01404-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01404-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01404-123">Child Elements</span></span>  
 <span data-ttu-id="01404-124">Keine</span><span class="sxs-lookup"><span data-stu-id="01404-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01404-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01404-125">Parent Elements</span></span>  
  
|<span data-ttu-id="01404-126">Element</span><span class="sxs-lookup"><span data-stu-id="01404-126">Element</span></span>|<span data-ttu-id="01404-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01404-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="01404-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="01404-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="01404-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="01404-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01404-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01404-130">Remarks</span></span>  
 <span data-ttu-id="01404-131">Beginnend mit .NET Framework 2.0, wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren von der Konfiguration des Computers gesteuert.</span><span class="sxs-lookup"><span data-stu-id="01404-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="01404-132">Wenn der Computer so konfiguriert ist, dass Algorithmen mit FIPS kompatibel sein müssen, und eine Klasse implementiert einen Algorithmus, der nicht mit FIPS kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse erstellen eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="01404-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="01404-133">Konstruktoren Auslösen einer <xref:System.InvalidOperationException> Ausnahme und `Create` Methoden lösen eine <xref:System.Reflection.TargetInvocationException> Ausnahme mit einer internen <xref:System.InvalidOperationException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="01404-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="01404-134">Wenn die Anwendung ausgeführt, auf Computern wird, deren Konfigurationen mit FIPS-Konformität erforderlich ist, und Ihre Anwendung verwendet einen Algorithmus, der nicht mit FIPS kompatibel ist, können dieses Element in der Konfigurationsdatei Sie zu verhindern, dass die common Language Runtime (CLR) Erzwingen der FIPS-Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="01404-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="01404-135">Dieses Element wurde in eingeführt, die [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01404-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="01404-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01404-136">Example</span></span>  
 <span data-ttu-id="01404-137">Das folgende Beispiel zeigt, wie zu verhindern, dass die CLR Erzwingen der FIPS-Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="01404-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01404-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01404-138">See Also</span></span>  
 [<span data-ttu-id="01404-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="01404-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="01404-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="01404-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="01404-141">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="01404-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
