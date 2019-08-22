---
title: <cryptoClass>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: c8076fba1ebae693aa5e4c80e822b9ae840ff1c5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664338"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="31c0a-102">\<cryptoClass-> Element</span><span class="sxs-lookup"><span data-stu-id="31c0a-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="31c0a-103">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="31c0a-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="31c0a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="31c0a-104">\<configuration></span></span>  
<span data-ttu-id="31c0a-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="31c0a-105">\<mscorlib></span></span>  
<span data-ttu-id="31c0a-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="31c0a-106">\<cryptographySettings></span></span>  
<span data-ttu-id="31c0a-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="31c0a-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="31c0a-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="31c0a-108">\<cryptoClasses></span></span>  
<span data-ttu-id="31c0a-109">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="31c0a-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31c0a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="31c0a-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31c0a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="31c0a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="31c0a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31c0a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31c0a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="31c0a-113">Attributes</span></span>  
  
|<span data-ttu-id="31c0a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="31c0a-114">Attribute</span></span>|<span data-ttu-id="31c0a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31c0a-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="31c0a-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="31c0a-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="31c0a-117">Enthält die Informationen für die Kryptografieklasse.</span><span class="sxs-lookup"><span data-stu-id="31c0a-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="31c0a-118">Verwenden Sie dieses Attribut, um einen Kurznamen für die Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="31c0a-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="31c0a-119">Sie müssen eine Zeichenfolge angeben, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="31c0a-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31c0a-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31c0a-120">Child Elements</span></span>  
 <span data-ttu-id="31c0a-121">Keine</span><span class="sxs-lookup"><span data-stu-id="31c0a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31c0a-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31c0a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="31c0a-123">Element</span><span class="sxs-lookup"><span data-stu-id="31c0a-123">Element</span></span>|<span data-ttu-id="31c0a-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31c0a-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="31c0a-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="31c0a-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="31c0a-126">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="31c0a-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="31c0a-127">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="31c0a-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="31c0a-128">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="31c0a-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="31c0a-129">Enthält das Element [\<cryptographySettings>](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="31c0a-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="31c0a-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31c0a-130">Example</span></span>  
 <span data-ttu-id="31c0a-131">Im folgenden Beispiel wird gezeigt, wie das  **\<cryptoClass >** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="31c0a-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="31c0a-132">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> die-Methode verwenden `MyCryptoRSAClass` , um ein-Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="31c0a-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="31c0a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31c0a-133">See also</span></span>

- [<span data-ttu-id="31c0a-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="31c0a-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="31c0a-135">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="31c0a-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="31c0a-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="31c0a-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="31c0a-137">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="31c0a-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
