---
title: <cryptoNameMapping>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: ff3300f57fd4681875e2791610cc5a0d0dcba31b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281475"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="e7d38-102">\<CryptoNameMapping >-Element</span><span class="sxs-lookup"><span data-stu-id="e7d38-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="e7d38-103">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="e7d38-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="e7d38-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e7d38-104">\<configuration></span></span>  
<span data-ttu-id="e7d38-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="e7d38-105">\<mscorlib></span></span>  
<span data-ttu-id="e7d38-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="e7d38-106">\<cryptographySettings></span></span>  
<span data-ttu-id="e7d38-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="e7d38-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d38-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7d38-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7d38-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e7d38-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e7d38-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7d38-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7d38-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e7d38-111">Attributes</span></span>  
 <span data-ttu-id="e7d38-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e7d38-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7d38-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7d38-113">Child Elements</span></span>  
  
|<span data-ttu-id="e7d38-114">Element</span><span class="sxs-lookup"><span data-stu-id="e7d38-114">Element</span></span>|<span data-ttu-id="e7d38-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7d38-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="e7d38-116">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e7d38-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="e7d38-117">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e7d38-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7d38-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7d38-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e7d38-119">Element</span><span class="sxs-lookup"><span data-stu-id="e7d38-119">Element</span></span>|<span data-ttu-id="e7d38-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7d38-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e7d38-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e7d38-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e7d38-122">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e7d38-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="e7d38-123">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="e7d38-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="e7d38-124">Enthält die \<CryptographySettings > Element.</span><span class="sxs-lookup"><span data-stu-id="e7d38-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e7d38-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7d38-125">Example</span></span>  
 <span data-ttu-id="e7d38-126">Das folgende Beispiel zeigt, wie Sie mit der  **\<CryptoNameMapping >** Element auf eine kryptografischen Klasse verweisen und die Runtime zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e7d38-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e7d38-127">Sie können dann an die Zeichenfolge "RSA" übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="e7d38-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7d38-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7d38-128">See also</span></span>
- [<span data-ttu-id="e7d38-129">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e7d38-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e7d38-130">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e7d38-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="e7d38-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e7d38-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="e7d38-132">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="e7d38-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
