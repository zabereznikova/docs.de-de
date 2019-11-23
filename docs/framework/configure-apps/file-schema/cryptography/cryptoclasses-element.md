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
ms.openlocfilehash: 89f1d89ea397794e366b53205ac23b94d7892869
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699752"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="3ee24-102">\<cryptoClasses >-Element</span><span class="sxs-lookup"><span data-stu-id="3ee24-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="3ee24-103">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3ee24-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="3ee24-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3ee24-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3ee24-105">&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3ee24-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="3ee24-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ee24-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="3ee24-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ee24-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="3ee24-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**cryptoClasses >**</span><span class="sxs-lookup"><span data-stu-id="3ee24-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ee24-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ee24-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ee24-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3ee24-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3ee24-111">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ee24-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ee24-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3ee24-112">Attributes</span></span>  
 <span data-ttu-id="3ee24-113">None.</span><span class="sxs-lookup"><span data-stu-id="3ee24-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3ee24-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ee24-114">Child Elements</span></span>  
  
|<span data-ttu-id="3ee24-115">Element</span><span class="sxs-lookup"><span data-stu-id="3ee24-115">Element</span></span>|<span data-ttu-id="3ee24-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ee24-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ee24-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="3ee24-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="3ee24-118">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3ee24-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ee24-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ee24-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3ee24-120">Element</span><span class="sxs-lookup"><span data-stu-id="3ee24-120">Element</span></span>|<span data-ttu-id="3ee24-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ee24-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3ee24-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3ee24-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="3ee24-123">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3ee24-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="3ee24-124">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="3ee24-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="3ee24-125">Enthält das `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="3ee24-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3ee24-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ee24-126">Example</span></span>  
 <span data-ttu-id="3ee24-127">Im folgenden Beispiel wird gezeigt, wie das **\<cryptoClass >** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3ee24-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="3ee24-128">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>-Methode übergeben und die <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>-Methode verwenden, um ein `MyCryptoRSAClass`-Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3ee24-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ee24-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ee24-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="3ee24-130">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="3ee24-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3ee24-131">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3ee24-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3ee24-132">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="3ee24-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="3ee24-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="3ee24-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="3ee24-134">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="3ee24-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
