---
title: '&lt;CryptoNameMapping&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2156c6441190b530c48a70e67e93e4806d20b199
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptonamemappinggt-element"></a><span data-ttu-id="f182f-102">&lt;CryptoNameMapping&gt; Element</span><span class="sxs-lookup"><span data-stu-id="f182f-102">&lt;cryptoNameMapping&gt; Element</span></span>
<span data-ttu-id="f182f-103">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="f182f-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="f182f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f182f-104">\<configuration></span></span>  
<span data-ttu-id="f182f-105">\<"mscorlib" ></span><span class="sxs-lookup"><span data-stu-id="f182f-105">\<mscorlib></span></span>  
<span data-ttu-id="f182f-106">\<CryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="f182f-106">\<cryptographySettings></span></span>  
<span data-ttu-id="f182f-107">\<CryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="f182f-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f182f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f182f-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f182f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f182f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f182f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f182f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f182f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f182f-111">Attributes</span></span>  
 <span data-ttu-id="f182f-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="f182f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f182f-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f182f-113">Child Elements</span></span>  
  
|<span data-ttu-id="f182f-114">Element</span><span class="sxs-lookup"><span data-stu-id="f182f-114">Element</span></span>|<span data-ttu-id="f182f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f182f-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="f182f-116">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f182f-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="f182f-117">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="f182f-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f182f-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f182f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f182f-119">Element</span><span class="sxs-lookup"><span data-stu-id="f182f-119">Element</span></span>|<span data-ttu-id="f182f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f182f-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f182f-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f182f-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f182f-122">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f182f-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="f182f-123">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="f182f-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="f182f-124">Enthält die \<CryptographySettings > Element.</span><span class="sxs-lookup"><span data-stu-id="f182f-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f182f-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f182f-125">Example</span></span>  
 <span data-ttu-id="f182f-126">Das folgende Beispiel zeigt, wie Sie die  **\<CryptoNameMapping >** Element auf eine kryptografischen Klasse verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f182f-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="f182f-127">Sie können dann die Zeichenfolge "RSA" übergeben, um die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="f182f-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f182f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f182f-128">See Also</span></span>  
 [<span data-ttu-id="f182f-129">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f182f-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="f182f-130">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f182f-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="f182f-131">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="f182f-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="f182f-132">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="f182f-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
