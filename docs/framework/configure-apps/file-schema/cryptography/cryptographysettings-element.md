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
ms.openlocfilehash: ec3a5a73caa901a21e22dbec7500af9153e01ef4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164137"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="64742-102">\<CryptographySettings >-Element</span><span class="sxs-lookup"><span data-stu-id="64742-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="64742-103">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="64742-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="64742-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="64742-104">\<configuration></span></span>  
<span data-ttu-id="64742-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="64742-105">\<mscorlib></span></span>  
<span data-ttu-id="64742-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="64742-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64742-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="64742-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64742-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="64742-108">Attributes and Elements</span></span>  
 <span data-ttu-id="64742-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64742-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64742-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="64742-110">Attributes</span></span>  
 <span data-ttu-id="64742-111">Keine</span><span class="sxs-lookup"><span data-stu-id="64742-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="64742-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64742-112">Child Elements</span></span>  
  
|<span data-ttu-id="64742-113">Element</span><span class="sxs-lookup"><span data-stu-id="64742-113">Element</span></span>|<span data-ttu-id="64742-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64742-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64742-115">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="64742-115">\<cryptoNameMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="64742-116">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="64742-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="64742-117">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="64742-117">\<oidMap></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="64742-118">Enthält die ASN. 1-Objekt-ID (OID)-Zuordnungen zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="64742-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64742-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64742-119">Parent Elements</span></span>  
  
|<span data-ttu-id="64742-120">Element</span><span class="sxs-lookup"><span data-stu-id="64742-120">Element</span></span>|<span data-ttu-id="64742-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64742-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="64742-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="64742-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="64742-123">Enthält die `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="64742-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="64742-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64742-124">Example</span></span>  
 <span data-ttu-id="64742-125">Im folgenden Beispiel wird gezeigt, wie mithilfe der  **\<CryptographySettings >** Element namenszuordnungen Kryptografie und OID-Zuordnungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="64742-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="64742-126">In diesem Beispiel wird die Laufzeit, damit <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> gibt eine `MyHashClass` Objekt und die `MyCryptoClass` Zuordnungen, die die Objekt-ID 1.3.36.2.1 Klasse.</span><span class="sxs-lookup"><span data-stu-id="64742-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64742-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64742-127">See also</span></span>

- [<span data-ttu-id="64742-128">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="64742-128">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="64742-129">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="64742-129">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="64742-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="64742-130">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
