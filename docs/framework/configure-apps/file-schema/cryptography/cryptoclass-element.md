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
ms.openlocfilehash: db3681ea141bb7e3905f6a470f5c74ce05f6ef4b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699788"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="1b8ca-102">\<cryptoclass >-Element</span><span class="sxs-lookup"><span data-stu-id="1b8ca-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="1b8ca-103">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="1b8ca-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1b8ca-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1b8ca-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1b8ca-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="1b8ca-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographysettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="1b8ca-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="1b8ca-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<cryptonamemapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="1b8ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="1b8ca-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0cryptoclasses >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="1b8ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>  
<span data-ttu-id="1b8ca-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1cryptoclass >**</span><span class="sxs-lookup"><span data-stu-id="1b8ca-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b8ca-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b8ca-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b8ca-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1b8ca-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1b8ca-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b8ca-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="1b8ca-113">Attributes</span></span>  
  
|<span data-ttu-id="1b8ca-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="1b8ca-114">Attribute</span></span>|<span data-ttu-id="1b8ca-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b8ca-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="1b8ca-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="1b8ca-117">Enthält die Informationen für die Kryptografieklasse.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="1b8ca-118">Verwenden Sie dieses Attribut, um einen Kurznamen für die Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="1b8ca-119">Sie müssen eine Zeichenfolge angeben, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b8ca-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b8ca-120">Child Elements</span></span>  
 <span data-ttu-id="1b8ca-121">Keine</span><span class="sxs-lookup"><span data-stu-id="1b8ca-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b8ca-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b8ca-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1b8ca-123">Element</span><span class="sxs-lookup"><span data-stu-id="1b8ca-123">Element</span></span>|<span data-ttu-id="1b8ca-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b8ca-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1b8ca-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="1b8ca-126">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element [\<nameEntry>](nameentry-element.md) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="1b8ca-127">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="1b8ca-128">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="1b8ca-129">Enthält das Element [\<cryptographySettings>](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="1b8ca-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1b8ca-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b8ca-130">Example</span></span>  
 <span data-ttu-id="1b8ca-131">Im folgenden Beispiel wird gezeigt, wie das **\<cryptoclass->** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="1b8ca-132">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>-Methode übergeben und die <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>-Methode verwenden, um ein `MyCryptoRSAClass`-Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1b8ca-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b8ca-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b8ca-133">See also</span></span>

- [<span data-ttu-id="1b8ca-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="1b8ca-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1b8ca-135">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1b8ca-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1b8ca-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="1b8ca-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="1b8ca-137">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="1b8ca-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
