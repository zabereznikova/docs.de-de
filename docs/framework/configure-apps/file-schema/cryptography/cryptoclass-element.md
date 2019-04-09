---
title: <cryptoClass> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: da78140806ab8dbe7b7cb5e321e82755774ff25d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103817"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="dc50e-102">\<CryptoClass >-Element</span><span class="sxs-lookup"><span data-stu-id="dc50e-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="dc50e-103">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dc50e-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="dc50e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dc50e-104">\<configuration></span></span>  
<span data-ttu-id="dc50e-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="dc50e-105">\<mscorlib></span></span>  
<span data-ttu-id="dc50e-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="dc50e-106">\<cryptographySettings></span></span>  
<span data-ttu-id="dc50e-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="dc50e-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="dc50e-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="dc50e-108">\<cryptoClasses></span></span>  
<span data-ttu-id="dc50e-109">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="dc50e-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc50e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc50e-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc50e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dc50e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dc50e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc50e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc50e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="dc50e-113">Attributes</span></span>  
  
|<span data-ttu-id="dc50e-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="dc50e-114">Attribute</span></span>|<span data-ttu-id="dc50e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc50e-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="dc50e-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="dc50e-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="dc50e-117">Enthält die Informationen für die Kryptografieklasse.</span><span class="sxs-lookup"><span data-stu-id="dc50e-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="dc50e-118">Verwenden Sie dieses Attribut, um einen kurzen Namen für die Klasse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="dc50e-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="dc50e-119">Geben Sie eine Zeichenfolge, die die in angegebenen Anforderungen erfüllt [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="dc50e-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc50e-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc50e-120">Child Elements</span></span>  
 <span data-ttu-id="dc50e-121">Keine</span><span class="sxs-lookup"><span data-stu-id="dc50e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc50e-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc50e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="dc50e-123">Element</span><span class="sxs-lookup"><span data-stu-id="dc50e-123">Element</span></span>|<span data-ttu-id="dc50e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc50e-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dc50e-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dc50e-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="dc50e-126">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="dc50e-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="dc50e-127">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="dc50e-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="dc50e-128">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="dc50e-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="dc50e-129">Enthält das Element [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="dc50e-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dc50e-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc50e-130">Example</span></span>  
 <span data-ttu-id="dc50e-131">Im folgenden Beispiel wird gezeigt, wie mithilfe der  **\<CryptoClass >** Element auf eine kryptografischen Klasse verweisen und die Runtime zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc50e-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="dc50e-132">Sie können dann an die Zeichenfolge "RSA" übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="dc50e-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc50e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc50e-133">See also</span></span>

- [<span data-ttu-id="dc50e-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="dc50e-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="dc50e-135">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="dc50e-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="dc50e-136">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="dc50e-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="dc50e-137">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="dc50e-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
