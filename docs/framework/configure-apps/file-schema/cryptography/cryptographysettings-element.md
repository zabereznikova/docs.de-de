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
ms.openlocfilehash: ca0a9a4b37f28eb03f58de4fd9b120cb7e654e0c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088646"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="4429a-102">\<> Element "cryptographySettings"</span><span class="sxs-lookup"><span data-stu-id="4429a-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="4429a-103">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4429a-103">Contains cryptography settings.</span></span>  

<span data-ttu-id="4429a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4429a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4429a-105">&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4429a-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="4429a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptographySettings >**</span><span class="sxs-lookup"><span data-stu-id="4429a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4429a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4429a-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4429a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4429a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4429a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4429a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4429a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4429a-110">Attributes</span></span>  
 <span data-ttu-id="4429a-111">Keine</span><span class="sxs-lookup"><span data-stu-id="4429a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4429a-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4429a-112">Child Elements</span></span>  
  
|<span data-ttu-id="4429a-113">Element</span><span class="sxs-lookup"><span data-stu-id="4429a-113">Element</span></span>|<span data-ttu-id="4429a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4429a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4429a-115">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="4429a-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="4429a-116">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="4429a-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="4429a-117">\<oidmap ></span><span class="sxs-lookup"><span data-stu-id="4429a-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="4429a-118">Enthält ASN. 1 objektbezeichnermappings (OID) zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="4429a-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4429a-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4429a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4429a-120">Element</span><span class="sxs-lookup"><span data-stu-id="4429a-120">Element</span></span>|<span data-ttu-id="4429a-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4429a-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4429a-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4429a-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="4429a-123">Enthält das `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="4429a-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4429a-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4429a-124">Example</span></span>  
 <span data-ttu-id="4429a-125">Im folgenden Beispiel wird gezeigt, wie das **\<cryptographySettings >** -Element verwendet wird, um kryptografienamenszuordnungen und OID-Zuordnungen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="4429a-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="4429a-126">In diesem Beispiel wird die Laufzeit so konfiguriert, dass <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> ein `MyHashClass`-Objekt zurückgibt, und die `MyCryptoClass`-Klasse wird dem Objekt Bezeichner 1.3.36.2.1 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4429a-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4429a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4429a-127">See also</span></span>

- [<span data-ttu-id="4429a-128">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="4429a-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4429a-129">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4429a-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4429a-130">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="4429a-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
