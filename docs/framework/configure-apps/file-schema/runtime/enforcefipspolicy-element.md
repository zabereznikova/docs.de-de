---
title: <enforceFIPSPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: 0d6dd291a24928487a040c0427f058dee80bf836
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117387"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="f062c-102">\<enforceFIPSPolicy>-Element</span><span class="sxs-lookup"><span data-stu-id="f062c-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="f062c-103">Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.</span><span class="sxs-lookup"><span data-stu-id="f062c-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="f062c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f062c-104">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f062c-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f062c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f062c-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f062c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f062c-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="f062c-107">Attributes</span></span>  
  
|<span data-ttu-id="f062c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f062c-108">Attribute</span></span>|<span data-ttu-id="f062c-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f062c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f062c-110">enabled</span><span class="sxs-lookup"><span data-stu-id="f062c-110">enabled</span></span>|<span data-ttu-id="f062c-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f062c-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="f062c-112">Gibt an, ob die Erzwingung einer Computer Konfigurations Anforderung aktiviert werden soll, dass Kryptografiealgorithmen mit "fps" kompatibel sein müssen.</span><span class="sxs-lookup"><span data-stu-id="f062c-112">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f062c-113">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="f062c-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="f062c-114">Wert</span><span class="sxs-lookup"><span data-stu-id="f062c-114">Value</span></span>|<span data-ttu-id="f062c-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f062c-115">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="f062c-116">Wenn Ihr Computer so konfiguriert ist, dass Kryptografiealgorithmen für die Kompatibilität mit der Konformität erforderlich sind, wird diese Anforderung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="f062c-116">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="f062c-117">Wenn eine Klasse einen Algorithmus implementiert, der nicht mit "fps" kompatibel ist, lösen die Konstruktoren oder `Create` Methoden für diese Klasse Ausnahmen aus, wenn Sie auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f062c-117">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="f062c-118">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f062c-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="f062c-119">Kryptografiealgorithmen, die von der Anwendung verwendet werden, müssen unabhängig von der Computerkonfiguration nicht mit dem PPS kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="f062c-119">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f062c-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f062c-120">Child Elements</span></span>  
 <span data-ttu-id="f062c-121">Keine</span><span class="sxs-lookup"><span data-stu-id="f062c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f062c-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f062c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f062c-123">Element</span><span class="sxs-lookup"><span data-stu-id="f062c-123">Element</span></span>|<span data-ttu-id="f062c-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f062c-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f062c-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f062c-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f062c-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f062c-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f062c-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f062c-127">Remarks</span></span>  
 <span data-ttu-id="f062c-128">Beginnend mit dem .NET Framework 2,0 wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren, von der Konfiguration des Computers gesteuert.</span><span class="sxs-lookup"><span data-stu-id="f062c-128">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="f062c-129">Wenn der Computer so konfiguriert ist, dass er Algorithmen erfordert, dass er mit der Verwendung von "fps" kompatibel ist, und eine Klasse einen Algorithmus implementiert, der nicht mit "fps" kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse zu erstellen, eine</span><span class="sxs-lookup"><span data-stu-id="f062c-129">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="f062c-130">Konstruktoren lösen eine <xref:System.InvalidOperationException> Ausnahme aus, und- `Create` Methoden lösen eine- <xref:System.Reflection.TargetInvocationException> Ausnahme mit einer inneren <xref:System.InvalidOperationException> Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="f062c-130">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="f062c-131">Wenn die Anwendung auf Computern ausgeführt wird, deren Konfigurationen mit dem Einsatz von "fps" kompatibel sein müssen, und die Anwendung einen Algorithmus verwendet, der nicht mit "fps" kompatibel ist, können Sie dieses Element in der Konfigurationsdatei verwenden, um zu verhindern, dass die Common Language Runtime (CLR) die Kompatibilität mit dem</span><span class="sxs-lookup"><span data-stu-id="f062c-131">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="f062c-132">Dieses Element wurde in .NET Framework 2,0 Service Pack 1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f062c-132">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f062c-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f062c-133">Example</span></span>  
 <span data-ttu-id="f062c-134">Im folgenden Beispiel wird gezeigt, wie verhindert wird, dass die CLR die Konformität mit der Konformität erzwingt.</span><span class="sxs-lookup"><span data-stu-id="f062c-134">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f062c-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f062c-135">See also</span></span>

- [<span data-ttu-id="f062c-136">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="f062c-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f062c-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f062c-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f062c-138">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="f062c-138">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
