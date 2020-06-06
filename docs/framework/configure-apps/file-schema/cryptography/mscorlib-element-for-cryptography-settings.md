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
ms.openlocfilehash: d1d805f7154c18dba2dcd4eb7228cc200d8da811
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155180"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="9c702-102">\<mscorlib>-Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="9c702-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="9c702-103">Enthält das- [ \<cryptographySettings> Element](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="9c702-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a><span data-ttu-id="9c702-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c702-104">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c702-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c702-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9c702-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c702-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c702-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="9c702-107">Attributes</span></span>  
 <span data-ttu-id="9c702-108">Keine</span><span class="sxs-lookup"><span data-stu-id="9c702-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c702-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c702-109">Child Elements</span></span>  
  
|<span data-ttu-id="9c702-110">Element</span><span class="sxs-lookup"><span data-stu-id="9c702-110">Element</span></span>|<span data-ttu-id="9c702-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c702-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="9c702-112">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9c702-112">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c702-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c702-113">Parent Elements</span></span>  
  
|<span data-ttu-id="9c702-114">Element</span><span class="sxs-lookup"><span data-stu-id="9c702-114">Element</span></span>|<span data-ttu-id="9c702-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c702-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9c702-116">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9c702-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9c702-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c702-117">Example</span></span>  
 <span data-ttu-id="9c702-118">Im folgenden Beispiel wird gezeigt, wie das **\<mscorlib>** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9c702-118">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="9c702-119">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und die- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> Methode verwenden, um ein-Objekt zurückzugeben `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="9c702-119">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c702-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c702-120">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="9c702-121">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="9c702-121">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9c702-122">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="9c702-122">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9c702-123">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="9c702-123">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="9c702-124">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="9c702-124">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
