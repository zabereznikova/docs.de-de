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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155231"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="ad70d-102">\<cryptographySettings>-Element</span><span class="sxs-lookup"><span data-stu-id="ad70d-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="ad70d-103">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ad70d-103">Contains cryptography settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**

## <a name="syntax"></a><span data-ttu-id="ad70d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad70d-104">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad70d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ad70d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ad70d-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad70d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad70d-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="ad70d-107">Attributes</span></span>  
 <span data-ttu-id="ad70d-108">Keine</span><span class="sxs-lookup"><span data-stu-id="ad70d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad70d-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad70d-109">Child Elements</span></span>  
  
|<span data-ttu-id="ad70d-110">Element</span><span class="sxs-lookup"><span data-stu-id="ad70d-110">Element</span></span>|<span data-ttu-id="ad70d-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ad70d-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](cryptonamemapping-element.md)|<span data-ttu-id="ad70d-112">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="ad70d-112">Contains mappings of classes to friendly names.</span></span>|  
|[\<oidMap>](oidmap-element.md)|<span data-ttu-id="ad70d-113">Enthält ASN. 1 objektbezeichnermappings (OID) zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="ad70d-113">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad70d-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad70d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ad70d-115">Element</span><span class="sxs-lookup"><span data-stu-id="ad70d-115">Element</span></span>|<span data-ttu-id="ad70d-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ad70d-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ad70d-117">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ad70d-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="ad70d-118">Enthält das- `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="ad70d-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ad70d-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad70d-119">Example</span></span>  
 <span data-ttu-id="ad70d-120">Im folgenden Beispiel wird gezeigt, wie mit dem **\<cryptographySettings>** -Element kryptografienamenszuordnungen und OID-Zuordnungen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ad70d-120">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="ad70d-121">In diesem Beispiel wird die Laufzeit so konfiguriert, dass <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> ein-Objekt zurückgibt, `MyHashClass` und die- `MyCryptoClass` Klasse wird dem Objekt Bezeichner 1.3.36.2.1 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ad70d-121">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ad70d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad70d-122">See also</span></span>

- [<span data-ttu-id="ad70d-123">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ad70d-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ad70d-124">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="ad70d-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ad70d-125">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="ad70d-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
