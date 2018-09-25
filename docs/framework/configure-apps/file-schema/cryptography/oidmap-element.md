---
title: '&lt;OidMap&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4ec2ba884f0f60182dd59bb6a4491e223f43ce1a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47073540"
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="79a3e-102">&lt;OidMap&gt; Element</span><span class="sxs-lookup"><span data-stu-id="79a3e-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="79a3e-103">Enthält die ASN. 1-Objekt-ID (OID)-Zuordnungen zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="79a3e-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="79a3e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="79a3e-104">\<configuration></span></span>  
<span data-ttu-id="79a3e-105">\<"mscorlib" ></span><span class="sxs-lookup"><span data-stu-id="79a3e-105">\<mscorlib></span></span>  
<span data-ttu-id="79a3e-106">\<CryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="79a3e-106">\<cryptographySettings></span></span>  
<span data-ttu-id="79a3e-107">\<OidMap ></span><span class="sxs-lookup"><span data-stu-id="79a3e-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a3e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="79a3e-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79a3e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="79a3e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="79a3e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79a3e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79a3e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="79a3e-111">Attributes</span></span>  
 <span data-ttu-id="79a3e-112">Keine</span><span class="sxs-lookup"><span data-stu-id="79a3e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="79a3e-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79a3e-113">Child Elements</span></span>  
  
|<span data-ttu-id="79a3e-114">Element</span><span class="sxs-lookup"><span data-stu-id="79a3e-114">Element</span></span>|<span data-ttu-id="79a3e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79a3e-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79a3e-116">\<OidEntry ></span><span class="sxs-lookup"><span data-stu-id="79a3e-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="79a3e-117">Ordnet einen ASN. 1-Objektbezeichner in einen Anzeigenamen an.</span><span class="sxs-lookup"><span data-stu-id="79a3e-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79a3e-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79a3e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="79a3e-119">Element</span><span class="sxs-lookup"><span data-stu-id="79a3e-119">Element</span></span>|<span data-ttu-id="79a3e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79a3e-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="79a3e-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="79a3e-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="79a3e-122">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="79a3e-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="79a3e-123">Enthält die `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="79a3e-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="79a3e-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79a3e-124">Example</span></span>  
 <span data-ttu-id="79a3e-125">Das folgende Beispiel zeigt, wie Sie mit der  **\<OidMap >** Element, in eine Zuordnung der OID für RIPEMD-160 Hashalgorithmus, der eine Implementierung dieses Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="79a3e-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79a3e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79a3e-126">See Also</span></span>  
 [<span data-ttu-id="79a3e-127">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="79a3e-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="79a3e-128">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="79a3e-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="79a3e-129">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="79a3e-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="79a3e-130">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="79a3e-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="79a3e-131">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="79a3e-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
