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
ms.openlocfilehash: f13243ddef7020f4d7a50e519ae8281702b0d261
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927420"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="f47a3-102">\<enforcemepspolicy > Element</span><span class="sxs-lookup"><span data-stu-id="f47a3-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="f47a3-103">Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.</span><span class="sxs-lookup"><span data-stu-id="f47a3-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="f47a3-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="f47a3-104">\<configuration> Element</span></span>  
<span data-ttu-id="f47a3-105">\<Runtime-> Element</span><span class="sxs-lookup"><span data-stu-id="f47a3-105">\<runtime> Element</span></span>  
<span data-ttu-id="f47a3-106">\<enforcemepspolicy > Element</span><span class="sxs-lookup"><span data-stu-id="f47a3-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f47a3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f47a3-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f47a3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f47a3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f47a3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f47a3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f47a3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f47a3-110">Attributes</span></span>  
  
|<span data-ttu-id="f47a3-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="f47a3-111">Attribute</span></span>|<span data-ttu-id="f47a3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f47a3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f47a3-113">enabled</span><span class="sxs-lookup"><span data-stu-id="f47a3-113">enabled</span></span>|<span data-ttu-id="f47a3-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f47a3-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="f47a3-115">Gibt an, ob die Erzwingung einer Computer Konfigurations Anforderung aktiviert werden soll, dass Kryptografiealgorithmen mit "fps" kompatibel sein müssen.</span><span class="sxs-lookup"><span data-stu-id="f47a3-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f47a3-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="f47a3-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="f47a3-117">Wert</span><span class="sxs-lookup"><span data-stu-id="f47a3-117">Value</span></span>|<span data-ttu-id="f47a3-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f47a3-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="f47a3-119">Wenn Ihr Computer so konfiguriert ist, dass Kryptografiealgorithmen für die Kompatibilität mit der Konformität erforderlich sind, wird diese Anforderung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="f47a3-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="f47a3-120">Wenn eine Klasse einen Algorithmus implementiert, der nicht mit "fps" kompatibel ist, lösen `Create` die Konstruktoren oder Methoden für diese Klasse Ausnahmen aus, wenn Sie auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f47a3-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="f47a3-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f47a3-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="f47a3-122">Kryptografiealgorithmen, die von der Anwendung verwendet werden, müssen unabhängig von der Computerkonfiguration nicht mit dem PPS kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="f47a3-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f47a3-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f47a3-123">Child Elements</span></span>  
 <span data-ttu-id="f47a3-124">Keine</span><span class="sxs-lookup"><span data-stu-id="f47a3-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f47a3-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f47a3-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f47a3-126">Element</span><span class="sxs-lookup"><span data-stu-id="f47a3-126">Element</span></span>|<span data-ttu-id="f47a3-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f47a3-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f47a3-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f47a3-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f47a3-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f47a3-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f47a3-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f47a3-130">Remarks</span></span>  
 <span data-ttu-id="f47a3-131">Beginnend mit dem .NET Framework 2,0 wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren, von der Konfiguration des Computers gesteuert.</span><span class="sxs-lookup"><span data-stu-id="f47a3-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="f47a3-132">Wenn der Computer so konfiguriert ist, dass er Algorithmen erfordert, dass er mit der Verwendung von "fps" kompatibel ist, und eine Klasse einen Algorithmus implementiert, der nicht mit "fps" kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse zu erstellen, eine</span><span class="sxs-lookup"><span data-stu-id="f47a3-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="f47a3-133">Konstruktoren lösen eine <xref:System.InvalidOperationException> Ausnahme aus, `Create` und-Methoden <xref:System.Reflection.TargetInvocationException> lösen eine-Ausnahme <xref:System.InvalidOperationException> mit einer inneren Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="f47a3-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="f47a3-134">Wenn die Anwendung auf Computern ausgeführt wird, deren Konfigurationen Kompatibilität mit dem-Konfigurationsserver erfordern, und die Anwendung einen Algorithmus verwendet, der nicht mit dem-fps kompatibel ist, können Sie dieses Element in der Konfigurationsdatei verwenden, um zu verhindern, dass die Common Language Runtime (CLR) von Erzwingen der Konformität mit dem PPS</span><span class="sxs-lookup"><span data-stu-id="f47a3-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="f47a3-135">Dieses Element wurde in .NET Framework 2,0 Service Pack 1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f47a3-135">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f47a3-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f47a3-136">Example</span></span>  
 <span data-ttu-id="f47a3-137">Im folgenden Beispiel wird gezeigt, wie verhindert wird, dass die CLR die Konformität mit der Konformität erzwingt.</span><span class="sxs-lookup"><span data-stu-id="f47a3-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f47a3-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f47a3-138">See also</span></span>

- [<span data-ttu-id="f47a3-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="f47a3-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f47a3-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f47a3-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f47a3-141">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="f47a3-141">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
