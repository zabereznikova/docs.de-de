---
title: <cryptoClasses>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 7a03729f075645a230c660ff4c6469e0f5f3a51e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220317"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="9c7b7-102">\<CryptoClasses >-Element</span><span class="sxs-lookup"><span data-stu-id="9c7b7-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="9c7b7-103">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="9c7b7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9c7b7-104">\<configuration></span></span>  
<span data-ttu-id="9c7b7-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="9c7b7-105">\<mscorlib></span></span>  
<span data-ttu-id="9c7b7-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="9c7b7-106">\<cryptographySettings></span></span>  
<span data-ttu-id="9c7b7-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="9c7b7-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="9c7b7-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="9c7b7-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7b7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c7b7-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c7b7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c7b7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9c7b7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c7b7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9c7b7-112">Attributes</span></span>  
 <span data-ttu-id="9c7b7-113">Keine</span><span class="sxs-lookup"><span data-stu-id="9c7b7-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c7b7-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c7b7-114">Child Elements</span></span>  
  
|<span data-ttu-id="9c7b7-115">Element</span><span class="sxs-lookup"><span data-stu-id="9c7b7-115">Element</span></span>|<span data-ttu-id="9c7b7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c7b7-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c7b7-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="9c7b7-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="9c7b7-118">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c7b7-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c7b7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9c7b7-120">Element</span><span class="sxs-lookup"><span data-stu-id="9c7b7-120">Element</span></span>|<span data-ttu-id="9c7b7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c7b7-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9c7b7-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="9c7b7-123">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="9c7b7-124">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="9c7b7-125">Enthält die `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9c7b7-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c7b7-126">Example</span></span>  
 <span data-ttu-id="9c7b7-127">Im folgenden Beispiel wird gezeigt, wie mithilfe der  **\<CryptoClass >** Element auf eine kryptografischen Klasse verweisen und die Runtime zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="9c7b7-128">Sie können dann an die Zeichenfolge "RSA" übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="9c7b7-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c7b7-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c7b7-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="9c7b7-130">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="9c7b7-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="9c7b7-131">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9c7b7-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="9c7b7-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="9c7b7-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="9c7b7-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="9c7b7-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="9c7b7-134">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="9c7b7-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
