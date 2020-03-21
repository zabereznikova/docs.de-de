---
title: <cryptographySettings>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: fe6de09213c6f980e8eb205a318aae50033b2a84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155231"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="1d2b7-102">\<kryptoographySettings> Element</span><span class="sxs-lookup"><span data-stu-id="1d2b7-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="1d2b7-103">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-103">Contains cryptography settings.</span></span>  

<span data-ttu-id="1d2b7-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1d2b7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1d2b7-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1d2b7-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="1d2b7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span><span class="sxs-lookup"><span data-stu-id="1d2b7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1d2b7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d2b7-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d2b7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1d2b7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1d2b7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d2b7-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="1d2b7-110">Attributes</span></span>  
 <span data-ttu-id="1d2b7-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d2b7-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d2b7-112">Child Elements</span></span>  
  
|<span data-ttu-id="1d2b7-113">Element</span><span class="sxs-lookup"><span data-stu-id="1d2b7-113">Element</span></span>|<span data-ttu-id="1d2b7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d2b7-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d2b7-115">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="1d2b7-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="1d2b7-116">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="1d2b7-117">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="1d2b7-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="1d2b7-118">Enthält ASN.1-Objektbezeichnerzuordnungen (OID) zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d2b7-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d2b7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1d2b7-120">Element</span><span class="sxs-lookup"><span data-stu-id="1d2b7-120">Element</span></span>|<span data-ttu-id="1d2b7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d2b7-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1d2b7-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="1d2b7-123">Enthält `cryptographySettings` das Element.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d2b7-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d2b7-124">Example</span></span>  
 <span data-ttu-id="1d2b7-125">Das folgende Beispiel zeigt, wie die \*\* \<CryptographySettings>-Element\*\* verwendet wird, um Kryptografienamenzuordnungen und OID-Zuordnungen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="1d2b7-126">In diesem Beispiel wird die <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> Laufzeit `MyHashClass` so `MyCryptoClass` konfiguriert, dass ein Objekt zurückgegeben wird und die Klasse dem Objektbezeichner 1.3.36.2.1 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1d2b7-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d2b7-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d2b7-127">See also</span></span>

- [<span data-ttu-id="1d2b7-128">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="1d2b7-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1d2b7-129">Kryptografie-Einstellungen Schema</span><span class="sxs-lookup"><span data-stu-id="1d2b7-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1d2b7-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="1d2b7-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
