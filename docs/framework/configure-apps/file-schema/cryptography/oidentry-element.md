---
title: '&lt;oidEntry&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 7c5309bc98a7781e82753869b1cf2bcf0a472327
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084093"
---
# <a name="ltoidentrygt-element"></a><span data-ttu-id="ce160-102">&lt;oidEntry&gt; Element</span><span class="sxs-lookup"><span data-stu-id="ce160-102">&lt;oidEntry&gt; Element</span></span>
<span data-ttu-id="ce160-103">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="ce160-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="ce160-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ce160-104">\<configuration></span></span>  
<span data-ttu-id="ce160-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="ce160-105">\<mscorlib></span></span>  
<span data-ttu-id="ce160-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="ce160-106">\<cryptographySettings></span></span>  
<span data-ttu-id="ce160-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="ce160-107">\<oidMap></span></span>  
<span data-ttu-id="ce160-108">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="ce160-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce160-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce160-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce160-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce160-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ce160-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce160-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce160-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce160-112">Attributes</span></span>  
  
|<span data-ttu-id="ce160-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="ce160-113">Attribute</span></span>|<span data-ttu-id="ce160-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce160-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce160-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="ce160-115">**OID**</span></span>|<span data-ttu-id="ce160-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce160-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ce160-117">Gibt an, das ASN. 1-Objektbezeichner für den Algorithmus, der von Ihrer Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="ce160-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="ce160-118">**name**</span><span class="sxs-lookup"><span data-stu-id="ce160-118">**name**</span></span>|<span data-ttu-id="ce160-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce160-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="ce160-120">Gibt den Wert für die **Namen** -Attribut in der [ \<NameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) Tag.</span><span class="sxs-lookup"><span data-stu-id="ce160-120">Specifies the value for the **name** attribute in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce160-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce160-121">Child Elements</span></span>  
 <span data-ttu-id="ce160-122">Keine</span><span class="sxs-lookup"><span data-stu-id="ce160-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce160-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce160-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ce160-124">Element</span><span class="sxs-lookup"><span data-stu-id="ce160-124">Element</span></span>|<span data-ttu-id="ce160-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce160-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ce160-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ce160-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="ce160-127">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ce160-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="ce160-128">Enthält die `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="ce160-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="ce160-129">Enthält die ASN. 1-Objekt-ID (OID)-Zuordnungen zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="ce160-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce160-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce160-130">Remarks</span></span>  
 <span data-ttu-id="ce160-131">ASN. 1-Objektbezeichner identifizieren Algorithmen in bestimmten kryptografischen Formaten.</span><span class="sxs-lookup"><span data-stu-id="ce160-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="ce160-132">Ordnen Sie Objekt-IDs aussagekräftigere Namen für die Algorithmen, die Sie ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="ce160-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce160-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce160-133">Example</span></span>  
 <span data-ttu-id="ce160-134">Das folgende Beispiel zeigt, wie Sie mit der  **\<OidEntry >** Element, das eine Objekt-ID für den Hashalgorithmus RIPEMD-160-Implementierung dieses Hashalgorithmus zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ce160-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce160-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce160-135">See also</span></span>
- [<span data-ttu-id="ce160-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ce160-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ce160-137">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ce160-137">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="ce160-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="ce160-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="ce160-139">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="ce160-139">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="ce160-140">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="ce160-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
