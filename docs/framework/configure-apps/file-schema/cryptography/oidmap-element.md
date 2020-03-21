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
ms.openlocfilehash: a28eaf68fe1e6ab3f26592eee5ae2d0f2e7a3256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155166"
---
# <a name="oidmap-element"></a><span data-ttu-id="e1ac6-102">\<oidMap> Element</span><span class="sxs-lookup"><span data-stu-id="e1ac6-102">\<oidMap> Element</span></span>
<span data-ttu-id="e1ac6-103">Enthält ASN.1-Objektbezeichnerzuordnungen (OID) zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="e1ac6-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

<span data-ttu-id="e1ac6-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1ac6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e1ac6-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e1ac6-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="e1ac6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1ac6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="e1ac6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="e1ac6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e1ac6-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1ac6-108">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1ac6-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1ac6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e1ac6-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1ac6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1ac6-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="e1ac6-111">Attributes</span></span>  
 <span data-ttu-id="e1ac6-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="e1ac6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1ac6-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1ac6-113">Child Elements</span></span>  
  
|<span data-ttu-id="e1ac6-114">Element</span><span class="sxs-lookup"><span data-stu-id="e1ac6-114">Element</span></span>|<span data-ttu-id="e1ac6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1ac6-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1ac6-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="e1ac6-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="e1ac6-117">Ordnet eine ASN.1-OID einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="e1ac6-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1ac6-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1ac6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e1ac6-119">Element</span><span class="sxs-lookup"><span data-stu-id="e1ac6-119">Element</span></span>|<span data-ttu-id="e1ac6-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1ac6-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e1ac6-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e1ac6-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e1ac6-122">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e1ac6-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="e1ac6-123">Enthält `cryptographySettings` das Element.</span><span class="sxs-lookup"><span data-stu-id="e1ac6-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e1ac6-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1ac6-124">Example</span></span>  
 <span data-ttu-id="e1ac6-125">Das folgende Beispiel zeigt, wie Sie das \*\* \<oidMap->-Element\*\* verwenden, um eine Zuordnung einer OID für den RIPEMD-160-Hashalgorithmus zu einer Implementierung dieses Hashalgorithmus zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="e1ac6-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e1ac6-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1ac6-126">See also</span></span>

- [<span data-ttu-id="e1ac6-127">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e1ac6-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e1ac6-128">Kryptografie-Einstellungen Schema</span><span class="sxs-lookup"><span data-stu-id="e1ac6-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e1ac6-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e1ac6-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e1ac6-130">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="e1ac6-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="e1ac6-131">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="e1ac6-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
