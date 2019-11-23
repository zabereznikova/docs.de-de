---
title: <mscorlib>-Element für Kryptografieeinstellungen
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: 4e2159cda5f35b5795804dede09ec17d07d71b23
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699743"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="d18ea-102">\<mscorlib-> Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="d18ea-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="d18ea-103">Enthält die [\<cryptographySettings-> Element](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="d18ea-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="d18ea-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d18ea-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d18ea-105">&nbsp;&nbsp; **\<mscorlib->**</span><span class="sxs-lookup"><span data-stu-id="d18ea-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d18ea-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d18ea-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d18ea-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d18ea-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d18ea-108">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d18ea-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d18ea-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d18ea-109">Attributes</span></span>  
 <span data-ttu-id="d18ea-110">None.</span><span class="sxs-lookup"><span data-stu-id="d18ea-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d18ea-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d18ea-111">Child Elements</span></span>  
  
|<span data-ttu-id="d18ea-112">Element</span><span class="sxs-lookup"><span data-stu-id="d18ea-112">Element</span></span>|<span data-ttu-id="d18ea-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d18ea-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="d18ea-114">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="d18ea-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d18ea-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d18ea-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d18ea-116">Element</span><span class="sxs-lookup"><span data-stu-id="d18ea-116">Element</span></span>|<span data-ttu-id="d18ea-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d18ea-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d18ea-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d18ea-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d18ea-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d18ea-119">Example</span></span>  
 <span data-ttu-id="d18ea-120">Im folgenden Beispiel wird gezeigt, wie das **\<mscorlib->** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d18ea-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="d18ea-121">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>-Methode übergeben und die <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>-Methode verwenden, um ein `MyCryptoRSAClass`-Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d18ea-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d18ea-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d18ea-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="d18ea-123">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="d18ea-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d18ea-124">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d18ea-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d18ea-125">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="d18ea-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="d18ea-126">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="d18ea-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
