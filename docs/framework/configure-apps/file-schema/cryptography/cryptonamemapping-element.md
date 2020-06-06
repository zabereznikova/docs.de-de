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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155218"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="0911f-102">\<cryptoNameMapping>-Element</span><span class="sxs-lookup"><span data-stu-id="0911f-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="0911f-103">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="0911f-103">Contains mappings of classes to friendly names.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**

## <a name="syntax"></a><span data-ttu-id="0911f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0911f-104">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0911f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0911f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0911f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0911f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0911f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0911f-107">Attributes</span></span>  
 <span data-ttu-id="0911f-108">Keine</span><span class="sxs-lookup"><span data-stu-id="0911f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0911f-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0911f-109">Child Elements</span></span>  
  
|<span data-ttu-id="0911f-110">Element</span><span class="sxs-lookup"><span data-stu-id="0911f-110">Element</span></span>|<span data-ttu-id="0911f-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0911f-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="0911f-112">Enthält eine Liste von Kryptografieklassen, die eine Zuordnung zu einem anzeigen Amen im- **\<nameEntry>** Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0911f-112">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="0911f-113">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="0911f-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0911f-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0911f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0911f-115">Element</span><span class="sxs-lookup"><span data-stu-id="0911f-115">Element</span></span>|<span data-ttu-id="0911f-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0911f-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0911f-117">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0911f-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="0911f-118">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="0911f-118">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="0911f-119">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="0911f-119">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="0911f-120">Enthält das- \<cryptographySettings> Element.</span><span class="sxs-lookup"><span data-stu-id="0911f-120">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0911f-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0911f-121">Example</span></span>  
 <span data-ttu-id="0911f-122">Im folgenden Beispiel wird gezeigt, wie das **\<cryptoNameMapping>** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0911f-122">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="0911f-123">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und die- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> Methode verwenden, um ein-Objekt zurückzugeben `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="0911f-123">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0911f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0911f-124">See also</span></span>

- [<span data-ttu-id="0911f-125">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="0911f-125">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0911f-126">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="0911f-126">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0911f-127">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="0911f-127">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="0911f-128">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="0911f-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
