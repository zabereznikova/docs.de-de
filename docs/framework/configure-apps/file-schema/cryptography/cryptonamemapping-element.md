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
ms.openlocfilehash: 87b24595f5013ad3b981256fd97bc758863c600b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921101"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="f6298-102">\<cryptoNameMapping-> Element</span><span class="sxs-lookup"><span data-stu-id="f6298-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="f6298-103">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="f6298-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="f6298-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f6298-104">\<configuration></span></span>  
<span data-ttu-id="f6298-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="f6298-105">\<mscorlib></span></span>  
<span data-ttu-id="f6298-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="f6298-106">\<cryptographySettings></span></span>  
<span data-ttu-id="f6298-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="f6298-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6298-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6298-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6298-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f6298-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f6298-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6298-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6298-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f6298-111">Attributes</span></span>  
 <span data-ttu-id="f6298-112">Keine</span><span class="sxs-lookup"><span data-stu-id="f6298-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f6298-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f6298-113">Child Elements</span></span>  
  
|<span data-ttu-id="f6298-114">Element</span><span class="sxs-lookup"><span data-stu-id="f6298-114">Element</span></span>|<span data-ttu-id="f6298-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6298-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="f6298-116">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f6298-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="f6298-117">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="f6298-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6298-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f6298-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f6298-119">Element</span><span class="sxs-lookup"><span data-stu-id="f6298-119">Element</span></span>|<span data-ttu-id="f6298-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6298-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f6298-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f6298-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f6298-122">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f6298-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="f6298-123">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="f6298-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="f6298-124">Enthält das \<cryptographySettings-> Element.</span><span class="sxs-lookup"><span data-stu-id="f6298-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f6298-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6298-125">Example</span></span>  
 <span data-ttu-id="f6298-126">Im folgenden Beispiel wird gezeigt, wie das  **\<cryptoNameMapping->** Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f6298-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="f6298-127">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> die-Methode verwenden `MyCryptoRSAClass` , um ein-Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f6298-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6298-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6298-128">See also</span></span>

- [<span data-ttu-id="f6298-129">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f6298-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f6298-130">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f6298-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f6298-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="f6298-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="f6298-132">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="f6298-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
