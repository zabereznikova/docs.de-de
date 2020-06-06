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
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088664"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="24530-102">\<cryptoClass>-Element</span><span class="sxs-lookup"><span data-stu-id="24530-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="24530-103">Enthält eine Kryptografieklasse, die eine Zuordnung zu einem anzeigen Amen im- [\<nameEntry>](nameentry-element.md) Element aufweist.</span><span class="sxs-lookup"><span data-stu-id="24530-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="24530-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24530-104">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24530-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="24530-105">Attributes and Elements</span></span>  
 <span data-ttu-id="24530-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="24530-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24530-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="24530-107">Attributes</span></span>  
  
|<span data-ttu-id="24530-108">attribute</span><span class="sxs-lookup"><span data-stu-id="24530-108">Attribute</span></span>|<span data-ttu-id="24530-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="24530-109">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="24530-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="24530-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="24530-111">Enthält die Informationen für die Kryptografieklasse.</span><span class="sxs-lookup"><span data-stu-id="24530-111">Contains the information for the cryptography class.</span></span> <span data-ttu-id="24530-112">Verwenden Sie dieses Attribut, um einen Kurznamen für die Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="24530-112">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="24530-113">Sie müssen eine Zeichenfolge angeben, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="24530-113">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24530-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24530-114">Child Elements</span></span>  
 <span data-ttu-id="24530-115">Keine</span><span class="sxs-lookup"><span data-stu-id="24530-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24530-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24530-116">Parent Elements</span></span>  
  
|<span data-ttu-id="24530-117">Element</span><span class="sxs-lookup"><span data-stu-id="24530-117">Element</span></span>|<span data-ttu-id="24530-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24530-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="24530-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="24530-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="24530-120">Enthält eine Liste von Kryptografieklassen, die eine Zuordnung zu einem anzeigen Amen im- [\<nameEntry>](nameentry-element.md) Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="24530-120">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="24530-121">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="24530-121">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="24530-122">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="24530-122">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="24530-123">Enthält das- [\<cryptographySettings>](cryptographysettings-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="24530-123">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="24530-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24530-124">Example</span></span>  
 <span data-ttu-id="24530-125">Im folgenden Beispiel wird gezeigt, wie das **\<cryptoClass>** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24530-125">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="24530-126">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und die- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> Methode verwenden, um ein-Objekt zurückzugeben `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="24530-126">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="24530-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24530-127">See also</span></span>

- [<span data-ttu-id="24530-128">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="24530-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="24530-129">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="24530-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="24530-130">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="24530-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="24530-131">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="24530-131">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
