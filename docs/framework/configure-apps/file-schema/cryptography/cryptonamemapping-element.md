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
ms.openlocfilehash: d31c5cd52ffe0e2a6eb5784735e76436d216444b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155218"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="c707e-102">\<cryptoNameMapping> Element</span><span class="sxs-lookup"><span data-stu-id="c707e-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="c707e-103">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="c707e-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="c707e-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c707e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c707e-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c707e-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="c707e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="c707e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="c707e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span><span class="sxs-lookup"><span data-stu-id="c707e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c707e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c707e-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c707e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c707e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c707e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c707e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c707e-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="c707e-111">Attributes</span></span>  
 <span data-ttu-id="c707e-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="c707e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c707e-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c707e-113">Child Elements</span></span>  
  
|<span data-ttu-id="c707e-114">Element</span><span class="sxs-lookup"><span data-stu-id="c707e-114">Element</span></span>|<span data-ttu-id="c707e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c707e-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="c707e-116">Enthält eine Liste von Kryptografieklassen, die \*\* \<\*\* eine Zuordnung zu einem Anzeigenamen im nameEntry>-Element haben.</span><span class="sxs-lookup"><span data-stu-id="c707e-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="c707e-117">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="c707e-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c707e-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c707e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c707e-119">Element</span><span class="sxs-lookup"><span data-stu-id="c707e-119">Element</span></span>|<span data-ttu-id="c707e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c707e-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c707e-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c707e-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="c707e-122">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="c707e-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="c707e-123">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="c707e-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="c707e-124">Enthält das Element \<cryptographySettings>.</span><span class="sxs-lookup"><span data-stu-id="c707e-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c707e-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c707e-125">Example</span></span>  
 <span data-ttu-id="c707e-126">Das folgende Beispiel zeigt, wie Sie das \*\* \<cryptoNameMapping>-Element\*\* verwenden, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c707e-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="c707e-127">Sie können dann die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> Methode übergeben und die <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> Methode verwenden, um ein `MyCryptoRSAClass` Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c707e-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c707e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c707e-128">See also</span></span>

- [<span data-ttu-id="c707e-129">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c707e-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c707e-130">Kryptografie-Einstellungen Schema</span><span class="sxs-lookup"><span data-stu-id="c707e-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c707e-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="c707e-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="c707e-132">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="c707e-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
