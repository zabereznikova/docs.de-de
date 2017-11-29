---
title: '&lt;OidEntry&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 12c3b87f1cec72798ea92357f34ecc25b7e6edcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltoidentrygt-element"></a><span data-ttu-id="f9ab9-102">&lt;OidEntry&gt; Element</span><span class="sxs-lookup"><span data-stu-id="f9ab9-102">&lt;oidEntry&gt; Element</span></span>
<span data-ttu-id="f9ab9-103">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="f9ab9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f9ab9-104">\<configuration></span></span>  
<span data-ttu-id="f9ab9-105">\<"mscorlib" ></span><span class="sxs-lookup"><span data-stu-id="f9ab9-105">\<mscorlib></span></span>  
<span data-ttu-id="f9ab9-106">\<CryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="f9ab9-106">\<cryptographySettings></span></span>  
<span data-ttu-id="f9ab9-107">\<OidMap ></span><span class="sxs-lookup"><span data-stu-id="f9ab9-107">\<oidMap></span></span>  
<span data-ttu-id="f9ab9-108">\<OidEntry ></span><span class="sxs-lookup"><span data-stu-id="f9ab9-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9ab9-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9ab9-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9ab9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ab9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f9ab9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9ab9-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9ab9-112">Attributes</span></span>  
  
|<span data-ttu-id="f9ab9-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f9ab9-113">Attribute</span></span>|<span data-ttu-id="f9ab9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9ab9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9ab9-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="f9ab9-115">**OID**</span></span>|<span data-ttu-id="f9ab9-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9ab9-117">Gibt die ASN. 1-OID für den Algorithmus, der von der Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="f9ab9-118">**name**</span><span class="sxs-lookup"><span data-stu-id="f9ab9-118">**name**</span></span>|<span data-ttu-id="f9ab9-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9ab9-120">Gibt den Wert für die **Namen** Attribut in der [ \<NameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) Tag.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-120">Specifies the value for the **name** attribute in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9ab9-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ab9-121">Child Elements</span></span>  
 <span data-ttu-id="f9ab9-122">Keine</span><span class="sxs-lookup"><span data-stu-id="f9ab9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9ab9-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ab9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f9ab9-124">Element</span><span class="sxs-lookup"><span data-stu-id="f9ab9-124">Element</span></span>|<span data-ttu-id="f9ab9-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9ab9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f9ab9-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f9ab9-127">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="f9ab9-128">Enthält die `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="f9ab9-129">Enthält die ASN. 1-Objekt-ID (OID)-Zuordnungen von Klassen.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9ab9-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9ab9-130">Remarks</span></span>  
 <span data-ttu-id="f9ab9-131">ASN. 1-Objektbezeichner identifizieren, in einigen Formaten kryptografischen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="f9ab9-132">Ordnen Sie Objektbezeichner Anzeigenamen für die Algorithmen, die Sie ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9ab9-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9ab9-133">Example</span></span>  
 <span data-ttu-id="f9ab9-134">Das folgende Beispiel zeigt, wie Sie die  **\<OidEntry >** -Element einen Objektbezeichner für die RIPEMD-160-Hashalgorithmus zu einer Implementierung dieses Hashalgorithmus zuordnen.</span><span class="sxs-lookup"><span data-stu-id="f9ab9-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9ab9-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9ab9-135">See Also</span></span>  
 [<span data-ttu-id="f9ab9-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f9ab9-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="f9ab9-137">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f9ab9-137">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="f9ab9-138">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="f9ab9-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="f9ab9-139">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="f9ab9-139">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="f9ab9-140">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="f9ab9-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
