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
ms.openlocfilehash: 6601417f0b80f623b7698c4b072c35eca44343b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732889"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="ff1fc-102">\<cryptoClasses >-Element</span><span class="sxs-lookup"><span data-stu-id="ff1fc-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="ff1fc-103">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="ff1fc-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ff1fc-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ff1fc-105">&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ff1fc-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="ff1fc-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff1fc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="ff1fc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff1fc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="ff1fc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**cryptoClasses >**</span><span class="sxs-lookup"><span data-stu-id="ff1fc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff1fc-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff1fc-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff1fc-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ff1fc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ff1fc-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff1fc-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="ff1fc-112">Attributes</span></span>  
 <span data-ttu-id="ff1fc-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff1fc-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff1fc-114">Child Elements</span></span>  
  
|<span data-ttu-id="ff1fc-115">Element</span><span class="sxs-lookup"><span data-stu-id="ff1fc-115">Element</span></span>|<span data-ttu-id="ff1fc-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff1fc-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff1fc-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="ff1fc-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="ff1fc-118">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff1fc-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff1fc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ff1fc-120">Element</span><span class="sxs-lookup"><span data-stu-id="ff1fc-120">Element</span></span>|<span data-ttu-id="ff1fc-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff1fc-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ff1fc-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="ff1fc-123">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="ff1fc-124">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="ff1fc-125">Enthält das `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff1fc-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff1fc-126">Example</span></span>  
 <span data-ttu-id="ff1fc-127">Im folgenden Beispiel wird gezeigt, wie das **\<cryptoClass >** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="ff1fc-128">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>-Methode übergeben und die <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>-Methode verwenden, um ein `MyCryptoRSAClass`-Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1fc-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff1fc-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff1fc-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="ff1fc-130">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ff1fc-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ff1fc-131">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ff1fc-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ff1fc-132">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="ff1fc-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="ff1fc-133">System. Security. Cryptography. CryptoConfig. kreatefromname</span><span class="sxs-lookup"><span data-stu-id="ff1fc-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="ff1fc-134">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="ff1fc-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
