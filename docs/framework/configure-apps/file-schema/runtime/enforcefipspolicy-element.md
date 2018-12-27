---
title: '&lt;EnforceFIPSPolicy&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0bffe72a4bcadb4a36a9ac54263d55e242ffc4d4
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612009"
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="45498-102">&lt;EnforceFIPSPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="45498-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="45498-103">Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.</span><span class="sxs-lookup"><span data-stu-id="45498-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="45498-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="45498-104">\<configuration> Element</span></span>  
<span data-ttu-id="45498-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="45498-105">\<runtime> Element</span></span>  
<span data-ttu-id="45498-106">\<EnforceFIPSPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="45498-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45498-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="45498-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45498-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="45498-108">Attributes and Elements</span></span>  
 <span data-ttu-id="45498-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="45498-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45498-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="45498-110">Attributes</span></span>  
  
|<span data-ttu-id="45498-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="45498-111">Attribute</span></span>|<span data-ttu-id="45498-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45498-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45498-113">enabled</span><span class="sxs-lookup"><span data-stu-id="45498-113">enabled</span></span>|<span data-ttu-id="45498-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="45498-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="45498-115">Gibt an, ob die Erzwingung von computerkonfigurationsanforderung, dass kryptografische Algorithmen mit FIPS konform sein müssen.</span><span class="sxs-lookup"><span data-stu-id="45498-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="45498-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="45498-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="45498-117">Wert</span><span class="sxs-lookup"><span data-stu-id="45498-117">Value</span></span>|<span data-ttu-id="45498-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45498-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="45498-119">Wenn Ihr Computer konfiguriert ist, um kryptografische Algorithmen, die mit FIPS konform sein müssen, wird die Anforderung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="45498-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="45498-120">Wenn eine Klasse einen Algorithmus implementiert, die nicht mit FIPS, die Konstruktoren kompatibel ist oder `Create` Methoden für diese Klasse die Ausnahmen auslösen, wenn sie auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="45498-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="45498-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="45498-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="45498-122">Kryptografische Algorithmen, die von der Anwendung verwendet werden, sind nicht erforderlich, um die Kompatibilität mit FIPS, unabhängig von der Konfiguration des Computers.</span><span class="sxs-lookup"><span data-stu-id="45498-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45498-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45498-123">Child Elements</span></span>  
 <span data-ttu-id="45498-124">Keine</span><span class="sxs-lookup"><span data-stu-id="45498-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45498-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45498-125">Parent Elements</span></span>  
  
|<span data-ttu-id="45498-126">Element</span><span class="sxs-lookup"><span data-stu-id="45498-126">Element</span></span>|<span data-ttu-id="45498-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45498-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="45498-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="45498-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="45498-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="45498-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45498-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45498-130">Remarks</span></span>  
 <span data-ttu-id="45498-131">Ab .NET Framework 2.0, wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren von der Konfiguration des Computers gesteuert.</span><span class="sxs-lookup"><span data-stu-id="45498-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="45498-132">Wenn der Computer so konfiguriert ist, dass die Algorithmen mit FIPS kompatibel sein müssen und eine Klasse implementiert einen Algorithmus, der nicht mit FIPS kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse erstellt eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="45498-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="45498-133">Auslösen von Konstruktoren eine <xref:System.InvalidOperationException> Ausnahme und `Create` Methoden lösen eine <xref:System.Reflection.TargetInvocationException> Ausnahme mit einer internen <xref:System.InvalidOperationException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="45498-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="45498-134">Wenn Ihre Anwendung ausgeführt, auf Computern wird, deren Konfigurationen erfordern, dass die Kompatibilität mit FIPS, und die Anwendung verwendet einen Algorithmus, der nicht mit FIPS kompatibel ist, können Sie dieses Element in der Konfigurationsdatei verwenden, um zu verhindern, dass die common Language Runtime (CLR) aus FIPS-Kompatibilität zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="45498-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="45498-135">Dieses Element wurde in eingeführt, die [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45498-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="45498-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45498-136">Example</span></span>  
 <span data-ttu-id="45498-137">Das folgende Beispiel zeigt, wie Sie verhindern, dass die CLR FIPS-Kompatibilität zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="45498-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45498-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45498-138">See Also</span></span>  
- [<span data-ttu-id="45498-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="45498-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="45498-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="45498-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="45498-141">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="45498-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
