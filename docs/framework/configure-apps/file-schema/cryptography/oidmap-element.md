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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155166"
---
# <a name="oidmap-element"></a><span data-ttu-id="2efd4-102">\<oidMap>-Element</span><span class="sxs-lookup"><span data-stu-id="2efd4-102">\<oidMap> Element</span></span>
<span data-ttu-id="2efd4-103">Enthält ASN. 1 objektbezeichnermappings (OID) zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="2efd4-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**

## <a name="syntax"></a><span data-ttu-id="2efd4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2efd4-104">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2efd4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2efd4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2efd4-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2efd4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2efd4-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="2efd4-107">Attributes</span></span>  
 <span data-ttu-id="2efd4-108">Keine</span><span class="sxs-lookup"><span data-stu-id="2efd4-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2efd4-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2efd4-109">Child Elements</span></span>  
  
|<span data-ttu-id="2efd4-110">Element</span><span class="sxs-lookup"><span data-stu-id="2efd4-110">Element</span></span>|<span data-ttu-id="2efd4-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2efd4-111">Description</span></span>|  
|-------------|-----------------|  
|[\<oidEntry>](oidentry-element.md)|<span data-ttu-id="2efd4-112">Ordnet eine ASN. 1-OID einem anzeigen Amen zu.</span><span class="sxs-lookup"><span data-stu-id="2efd4-112">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2efd4-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2efd4-113">Parent Elements</span></span>  
  
|<span data-ttu-id="2efd4-114">Element</span><span class="sxs-lookup"><span data-stu-id="2efd4-114">Element</span></span>|<span data-ttu-id="2efd4-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2efd4-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2efd4-116">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2efd4-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="2efd4-117">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="2efd4-117">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="2efd4-118">Enthält das- `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="2efd4-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2efd4-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2efd4-119">Example</span></span>  
 <span data-ttu-id="2efd4-120">Im folgenden Beispiel wird gezeigt, wie das-Element verwendet wird **\<oidMap>** , um eine Zuordnung einer OID für den RIPEMD-160-Hash Algorithmus zu einer Implementierung dieses Hash Algorithmus zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="2efd4-120">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2efd4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2efd4-121">See also</span></span>

- [<span data-ttu-id="2efd4-122">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2efd4-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2efd4-123">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="2efd4-123">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2efd4-124">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="2efd4-124">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="2efd4-125">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="2efd4-125">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="2efd4-126">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="2efd4-126">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
