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
ms.openlocfilehash: f7fe6d02b4697af3a1d0d04471a2736045fc9ecc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181803"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="26bda-102">\<cryptoClass>-Element</span><span class="sxs-lookup"><span data-stu-id="26bda-102">\<cryptoClass> Element</span></span>

<span data-ttu-id="26bda-103">Enthält eine Kryptografieklasse, die eine Zuordnung zu einem anzeigen Amen im- [\<nameEntry>](nameentry-element.md) Element aufweist.</span><span class="sxs-lookup"><span data-stu-id="26bda-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="26bda-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26bda-104">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26bda-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="26bda-105">Attributes and Elements</span></span>  

 <span data-ttu-id="26bda-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="26bda-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26bda-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="26bda-107">Attributes</span></span>  
  
|<span data-ttu-id="26bda-108">attribute</span><span class="sxs-lookup"><span data-stu-id="26bda-108">Attribute</span></span>|<span data-ttu-id="26bda-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26bda-109">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="26bda-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="26bda-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="26bda-111">Enthält die Informationen für die Kryptografieklasse.</span><span class="sxs-lookup"><span data-stu-id="26bda-111">Contains the information for the cryptography class.</span></span> <span data-ttu-id="26bda-112">Verwenden Sie dieses Attribut, um einen Kurznamen für die Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26bda-112">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="26bda-113">Sie müssen eine Zeichenfolge angeben, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="26bda-113">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26bda-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26bda-114">Child Elements</span></span>  

 <span data-ttu-id="26bda-115">Keine</span><span class="sxs-lookup"><span data-stu-id="26bda-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26bda-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26bda-116">Parent Elements</span></span>  
  
|<span data-ttu-id="26bda-117">Element</span><span class="sxs-lookup"><span data-stu-id="26bda-117">Element</span></span>|<span data-ttu-id="26bda-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26bda-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="26bda-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="26bda-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="26bda-120">Enthält eine Liste von Kryptografieklassen, die eine Zuordnung zu einem anzeigen Amen im- [\<nameEntry>](nameentry-element.md) Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="26bda-120">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="26bda-121">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="26bda-121">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="26bda-122">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="26bda-122">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="26bda-123">Enthält das- [\<cryptographySettings>](cryptographysettings-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="26bda-123">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="26bda-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26bda-124">Example</span></span>  

 <span data-ttu-id="26bda-125">Im folgenden Beispiel wird gezeigt, wie das **\<cryptoClass>** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="26bda-125">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="26bda-126">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und die- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> Methode verwenden, um ein-Objekt zurückzugeben `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="26bda-126">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="26bda-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26bda-127">See also</span></span>

- [<span data-ttu-id="26bda-128">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="26bda-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="26bda-129">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="26bda-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="26bda-130">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="26bda-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="26bda-131">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="26bda-131">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
