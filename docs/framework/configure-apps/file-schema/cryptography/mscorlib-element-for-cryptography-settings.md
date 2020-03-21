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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155180"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="42e1d-102">\<mscorlib> Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="42e1d-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="42e1d-103">Enthält das [ \<cryptographySettings>-Element](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="42e1d-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="42e1d-104">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="42e1d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="42e1d-105">&nbsp;&nbsp;**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="42e1d-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e1d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="42e1d-106">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42e1d-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42e1d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="42e1d-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42e1d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42e1d-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="42e1d-109">Attributes</span></span>  
 <span data-ttu-id="42e1d-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="42e1d-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="42e1d-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42e1d-111">Child Elements</span></span>  
  
|<span data-ttu-id="42e1d-112">Element</span><span class="sxs-lookup"><span data-stu-id="42e1d-112">Element</span></span>|<span data-ttu-id="42e1d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42e1d-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="42e1d-114">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="42e1d-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42e1d-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42e1d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="42e1d-116">Element</span><span class="sxs-lookup"><span data-stu-id="42e1d-116">Element</span></span>|<span data-ttu-id="42e1d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42e1d-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="42e1d-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="42e1d-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="42e1d-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="42e1d-119">Example</span></span>  
 <span data-ttu-id="42e1d-120">Das folgende Beispiel zeigt, wie Sie das \*\* \<mscorlib->-Element\*\* verwenden, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="42e1d-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="42e1d-121">Sie können dann die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> Methode übergeben und die <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> Methode verwenden, um ein `MyCryptoRSAClass` Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="42e1d-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="42e1d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42e1d-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="42e1d-123">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="42e1d-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="42e1d-124">Kryptografie-Einstellungen Schema</span><span class="sxs-lookup"><span data-stu-id="42e1d-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="42e1d-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="42e1d-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="42e1d-126">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="42e1d-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
