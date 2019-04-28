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
ms.openlocfilehash: ec328bc4c63bd4754c6f975ac03e610718304245
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674740"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="5aa22-102">\<"mscorlib" >-Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="5aa22-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="5aa22-103">Enthält die [ \<CryptographySettings >-Element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="5aa22-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="5aa22-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5aa22-104">\<configuration></span></span>  
<span data-ttu-id="5aa22-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="5aa22-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aa22-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5aa22-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5aa22-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5aa22-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5aa22-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5aa22-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5aa22-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="5aa22-109">Attributes</span></span>  
 <span data-ttu-id="5aa22-110">Keine</span><span class="sxs-lookup"><span data-stu-id="5aa22-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5aa22-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5aa22-111">Child Elements</span></span>  
  
|<span data-ttu-id="5aa22-112">Element</span><span class="sxs-lookup"><span data-stu-id="5aa22-112">Element</span></span>|<span data-ttu-id="5aa22-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5aa22-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="5aa22-114">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5aa22-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5aa22-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5aa22-115">Parent Elements</span></span>  
  
|<span data-ttu-id="5aa22-116">Element</span><span class="sxs-lookup"><span data-stu-id="5aa22-116">Element</span></span>|<span data-ttu-id="5aa22-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5aa22-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5aa22-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5aa22-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5aa22-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5aa22-119">Example</span></span>  
 <span data-ttu-id="5aa22-120">Das folgende Beispiel zeigt, wie Sie mit der  **\<"mscorlib" >** Element auf eine kryptografischen Klasse verweisen und die Runtime zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5aa22-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="5aa22-121">Sie können dann an die Zeichenfolge "RSA" übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="5aa22-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5aa22-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5aa22-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="5aa22-123">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="5aa22-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="5aa22-124">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5aa22-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="5aa22-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="5aa22-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="5aa22-126">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="5aa22-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
