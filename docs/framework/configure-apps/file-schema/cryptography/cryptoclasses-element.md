---
title: '&lt;CryptoClasses&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e3bc8fbb103d59b825e07cc52b155f1ea8061f31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649374"
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="04c08-102">&lt;CryptoClasses&gt; Element</span><span class="sxs-lookup"><span data-stu-id="04c08-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="04c08-103">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="04c08-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="04c08-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="04c08-104">\<configuration></span></span>  
<span data-ttu-id="04c08-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="04c08-105">\<mscorlib></span></span>  
<span data-ttu-id="04c08-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="04c08-106">\<cryptographySettings></span></span>  
<span data-ttu-id="04c08-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="04c08-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="04c08-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="04c08-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c08-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="04c08-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04c08-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="04c08-110">Attributes and Elements</span></span>  
 <span data-ttu-id="04c08-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="04c08-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04c08-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="04c08-112">Attributes</span></span>  
 <span data-ttu-id="04c08-113">Keine</span><span class="sxs-lookup"><span data-stu-id="04c08-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="04c08-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04c08-114">Child Elements</span></span>  
  
|<span data-ttu-id="04c08-115">Element</span><span class="sxs-lookup"><span data-stu-id="04c08-115">Element</span></span>|<span data-ttu-id="04c08-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04c08-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04c08-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="04c08-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="04c08-118">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="04c08-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04c08-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04c08-119">Parent Elements</span></span>  
  
|<span data-ttu-id="04c08-120">Element</span><span class="sxs-lookup"><span data-stu-id="04c08-120">Element</span></span>|<span data-ttu-id="04c08-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04c08-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="04c08-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="04c08-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="04c08-123">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="04c08-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="04c08-124">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="04c08-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="04c08-125">Enthält die `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="04c08-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="04c08-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04c08-126">Example</span></span>  
 <span data-ttu-id="04c08-127">Im folgenden Beispiel wird gezeigt, wie mithilfe der  **\<CryptoClass >** Element auf eine kryptografischen Klasse verweisen und die Runtime zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="04c08-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="04c08-128">Sie können dann an die Zeichenfolge "RSA" übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="04c08-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="04c08-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04c08-129">See also</span></span>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="04c08-130">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="04c08-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="04c08-131">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="04c08-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="04c08-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="04c08-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="04c08-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="04c08-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="04c08-134">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="04c08-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
