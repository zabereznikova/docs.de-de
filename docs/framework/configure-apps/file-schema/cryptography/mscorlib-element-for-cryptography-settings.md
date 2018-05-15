---
title: '&lt;"mscorlib"&gt; -Element für Kryptografieeinstellungen'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 292937000eb1baca191c0960e8e496a128ee4696
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a><span data-ttu-id="a00a4-102">&lt;"mscorlib"&gt; -Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="a00a4-102">&lt;mscorlib&gt; Element for Cryptography Settings</span></span>
<span data-ttu-id="a00a4-103">Enthält die [ \<CryptographySettings >-Element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="a00a4-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="a00a4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a00a4-104">\<configuration></span></span>  
<span data-ttu-id="a00a4-105">\<"mscorlib" ></span><span class="sxs-lookup"><span data-stu-id="a00a4-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a00a4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a00a4-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a00a4-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a00a4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a00a4-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a00a4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a00a4-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="a00a4-109">Attributes</span></span>  
 <span data-ttu-id="a00a4-110">Keine</span><span class="sxs-lookup"><span data-stu-id="a00a4-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a00a4-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a00a4-111">Child Elements</span></span>  
  
|<span data-ttu-id="a00a4-112">Element</span><span class="sxs-lookup"><span data-stu-id="a00a4-112">Element</span></span>|<span data-ttu-id="a00a4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a00a4-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="a00a4-114">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a00a4-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a00a4-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a00a4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a00a4-116">Element</span><span class="sxs-lookup"><span data-stu-id="a00a4-116">Element</span></span>|<span data-ttu-id="a00a4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a00a4-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a00a4-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a00a4-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a00a4-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a00a4-119">Example</span></span>  
 <span data-ttu-id="a00a4-120">Das folgende Beispiel zeigt, wie Sie die  **\<"mscorlib" >** Element auf eine kryptografischen Klasse verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a00a4-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="a00a4-121">Sie können dann die Zeichenfolge "RSA" übergeben, um die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a00a4-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a00a4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a00a4-122">See Also</span></span>  
 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="a00a4-123">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a00a4-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a00a4-124">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a00a4-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="a00a4-125">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="a00a4-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="a00a4-126">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="a00a4-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
