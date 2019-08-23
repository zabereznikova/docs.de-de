---
title: <oidMap>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: d2929167f5a7de96a868cd1ac884d2203d09dfb6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927526"
---
# <a name="oidmap-element"></a><span data-ttu-id="bb3ff-102">\<oidmap-> Element</span><span class="sxs-lookup"><span data-stu-id="bb3ff-102">\<oidMap> Element</span></span>
<span data-ttu-id="bb3ff-103">Enthält ASN. 1 objektbezeichnermappings (OID) zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="bb3ff-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="bb3ff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb3ff-104">\<configuration></span></span>  
<span data-ttu-id="bb3ff-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="bb3ff-105">\<mscorlib></span></span>  
<span data-ttu-id="bb3ff-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="bb3ff-106">\<cryptographySettings></span></span>  
<span data-ttu-id="bb3ff-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="bb3ff-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3ff-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb3ff-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb3ff-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb3ff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bb3ff-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb3ff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb3ff-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb3ff-111">Attributes</span></span>  
 <span data-ttu-id="bb3ff-112">Keine</span><span class="sxs-lookup"><span data-stu-id="bb3ff-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb3ff-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb3ff-113">Child Elements</span></span>  
  
|<span data-ttu-id="bb3ff-114">Element</span><span class="sxs-lookup"><span data-stu-id="bb3ff-114">Element</span></span>|<span data-ttu-id="bb3ff-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb3ff-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb3ff-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="bb3ff-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="bb3ff-117">Ordnet eine ASN. 1-OID einem anzeigen Amen zu.</span><span class="sxs-lookup"><span data-stu-id="bb3ff-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb3ff-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb3ff-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bb3ff-119">Element</span><span class="sxs-lookup"><span data-stu-id="bb3ff-119">Element</span></span>|<span data-ttu-id="bb3ff-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb3ff-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb3ff-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bb3ff-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="bb3ff-122">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="bb3ff-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="bb3ff-123">Enthält das `cryptographySettings` -Element.</span><span class="sxs-lookup"><span data-stu-id="bb3ff-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bb3ff-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb3ff-124">Example</span></span>  
 <span data-ttu-id="bb3ff-125">Im folgenden Beispiel wird gezeigt, wie das  **\<oidmap->** -Element verwendet wird, um eine Zuordnung einer OID für den RIPEMD-160-Hash Algorithmus zu einer Implementierung dieses Hash Algorithmus zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="bb3ff-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bb3ff-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb3ff-126">See also</span></span>

- [<span data-ttu-id="bb3ff-127">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="bb3ff-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bb3ff-128">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="bb3ff-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bb3ff-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="bb3ff-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="bb3ff-130">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="bb3ff-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="bb3ff-131">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="bb3ff-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
