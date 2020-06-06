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
ms.openlocfilehash: c93fadf51297d59ab499e25de283700364903049
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155245"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="6164c-102">\<cryptoClasses>-Element</span><span class="sxs-lookup"><span data-stu-id="6164c-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="6164c-103">Enthält eine Liste von Kryptografieklassen, die eine Zuordnung zu einem anzeigen Amen im- [\<nameEntry>](nameentry-element.md) Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6164c-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**  
  
## <a name="syntax"></a><span data-ttu-id="6164c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6164c-104">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6164c-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6164c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6164c-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6164c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6164c-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="6164c-107">Attributes</span></span>  
 <span data-ttu-id="6164c-108">Keine</span><span class="sxs-lookup"><span data-stu-id="6164c-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6164c-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6164c-109">Child Elements</span></span>  
  
|<span data-ttu-id="6164c-110">Element</span><span class="sxs-lookup"><span data-stu-id="6164c-110">Element</span></span>|<span data-ttu-id="6164c-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6164c-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|<span data-ttu-id="6164c-112">Enthält eine Kryptografieklasse, die eine Zuordnung zu einem anzeigen Amen im- **\<nameEntry>** Element aufweist.</span><span class="sxs-lookup"><span data-stu-id="6164c-112">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6164c-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6164c-113">Parent Elements</span></span>  
  
|<span data-ttu-id="6164c-114">Element</span><span class="sxs-lookup"><span data-stu-id="6164c-114">Element</span></span>|<span data-ttu-id="6164c-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6164c-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6164c-116">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6164c-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="6164c-117">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6164c-117">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="6164c-118">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="6164c-118">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="6164c-119">Enthält das- `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="6164c-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6164c-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6164c-120">Example</span></span>  
 <span data-ttu-id="6164c-121">Im folgenden Beispiel wird gezeigt, wie das **\<cryptoClass>** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6164c-121">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="6164c-122">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und die- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> Methode verwenden, um ein-Objekt zurückzugeben `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="6164c-122">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6164c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6164c-123">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="6164c-124">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="6164c-124">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6164c-125">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="6164c-125">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6164c-126">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="6164c-126">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="6164c-127">System. Security. Cryptography. CryptoConfig. kreatefromname</span><span class="sxs-lookup"><span data-stu-id="6164c-127">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="6164c-128">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="6164c-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
