---
title: <enforceFIPSPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1aa958e15449949a1b7ca740198fff71295b2ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704962"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="cd5a0-102">\<EnforceFIPSPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="cd5a0-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="cd5a0-103">Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="cd5a0-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="cd5a0-104">\<configuration> Element</span></span>  
<span data-ttu-id="cd5a0-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="cd5a0-105">\<runtime> Element</span></span>  
<span data-ttu-id="cd5a0-106">\<EnforceFIPSPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="cd5a0-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd5a0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd5a0-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd5a0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd5a0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cd5a0-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd5a0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd5a0-110">Attributes</span></span>  
  
|<span data-ttu-id="cd5a0-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="cd5a0-111">Attribute</span></span>|<span data-ttu-id="cd5a0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd5a0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd5a0-113">enabled</span><span class="sxs-lookup"><span data-stu-id="cd5a0-113">enabled</span></span>|<span data-ttu-id="cd5a0-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cd5a0-115">Gibt an, ob die Erzwingung von computerkonfigurationsanforderung, dass kryptografische Algorithmen mit FIPS konform sein müssen.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cd5a0-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="cd5a0-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="cd5a0-117">Wert</span><span class="sxs-lookup"><span data-stu-id="cd5a0-117">Value</span></span>|<span data-ttu-id="cd5a0-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd5a0-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="cd5a0-119">Wenn Ihr Computer konfiguriert ist, um kryptografische Algorithmen, die mit FIPS konform sein müssen, wird die Anforderung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="cd5a0-120">Wenn eine Klasse einen Algorithmus implementiert, die nicht mit FIPS, die Konstruktoren kompatibel ist oder `Create` Methoden für diese Klasse die Ausnahmen auslösen, wenn sie auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="cd5a0-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="cd5a0-122">Kryptografische Algorithmen, die von der Anwendung verwendet werden, sind nicht erforderlich, um die Kompatibilität mit FIPS, unabhängig von der Konfiguration des Computers.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd5a0-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd5a0-123">Child Elements</span></span>  
 <span data-ttu-id="cd5a0-124">Keine</span><span class="sxs-lookup"><span data-stu-id="cd5a0-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd5a0-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd5a0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="cd5a0-126">Element</span><span class="sxs-lookup"><span data-stu-id="cd5a0-126">Element</span></span>|<span data-ttu-id="cd5a0-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd5a0-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cd5a0-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cd5a0-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd5a0-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd5a0-130">Remarks</span></span>  
 <span data-ttu-id="cd5a0-131">Ab .NET Framework 2.0, wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren von der Konfiguration des Computers gesteuert.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="cd5a0-132">Wenn der Computer so konfiguriert ist, dass die Algorithmen mit FIPS kompatibel sein müssen und eine Klasse implementiert einen Algorithmus, der nicht mit FIPS kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse erstellt eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="cd5a0-133">Auslösen von Konstruktoren eine <xref:System.InvalidOperationException> Ausnahme und `Create` Methoden lösen eine <xref:System.Reflection.TargetInvocationException> Ausnahme mit einer internen <xref:System.InvalidOperationException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="cd5a0-134">Wenn Ihre Anwendung ausgeführt, auf Computern wird, deren Konfigurationen erfordern, dass die Kompatibilität mit FIPS, und die Anwendung verwendet einen Algorithmus, der nicht mit FIPS kompatibel ist, können Sie dieses Element in der Konfigurationsdatei verwenden, um zu verhindern, dass die common Language Runtime (CLR) aus FIPS-Kompatibilität zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="cd5a0-135">Dieses Element wurde in eingeführt, die [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd5a0-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd5a0-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd5a0-136">Example</span></span>  
 <span data-ttu-id="cd5a0-137">Das folgende Beispiel zeigt, wie Sie verhindern, dass die CLR FIPS-Kompatibilität zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="cd5a0-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd5a0-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd5a0-138">See also</span></span>

- [<span data-ttu-id="cd5a0-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="cd5a0-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="cd5a0-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="cd5a0-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="cd5a0-141">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="cd5a0-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
