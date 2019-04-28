---
title: <nameEntry>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 97521ba9073820beeea62f5fc7cab480b5422fb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705180"
---
# <a name="nameentry-element"></a><span data-ttu-id="74d3b-102">\<NameEntry >-Element</span><span class="sxs-lookup"><span data-stu-id="74d3b-102">\<nameEntry> Element</span></span>
<span data-ttu-id="74d3b-103">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="74d3b-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="74d3b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="74d3b-104">\<configuration></span></span>  
<span data-ttu-id="74d3b-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="74d3b-105">\<mscorlib></span></span>  
<span data-ttu-id="74d3b-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="74d3b-106">\<cryptographySettings></span></span>  
<span data-ttu-id="74d3b-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="74d3b-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="74d3b-108">\<nameEntry></span><span class="sxs-lookup"><span data-stu-id="74d3b-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d3b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="74d3b-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74d3b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="74d3b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="74d3b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74d3b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74d3b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="74d3b-112">Attributes</span></span>  
  
|<span data-ttu-id="74d3b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="74d3b-113">Attribute</span></span>|<span data-ttu-id="74d3b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74d3b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74d3b-115">**name**</span><span class="sxs-lookup"><span data-stu-id="74d3b-115">**name**</span></span>|<span data-ttu-id="74d3b-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="74d3b-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="74d3b-117">Gibt den Anzeigenamen des Algorithmus, den die Kryptografieklasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="74d3b-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="74d3b-118">**class**</span><span class="sxs-lookup"><span data-stu-id="74d3b-118">**class**</span></span>|<span data-ttu-id="74d3b-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="74d3b-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="74d3b-120">Gibt den Wert für die **Namen** -Attribut in der [ \<CryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="74d3b-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74d3b-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74d3b-121">Child Elements</span></span>  
 <span data-ttu-id="74d3b-122">Keine</span><span class="sxs-lookup"><span data-stu-id="74d3b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74d3b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74d3b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="74d3b-124">Element</span><span class="sxs-lookup"><span data-stu-id="74d3b-124">Element</span></span>|<span data-ttu-id="74d3b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74d3b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="74d3b-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="74d3b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="74d3b-127">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="74d3b-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74d3b-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74d3b-128">Remarks</span></span>  
 <span data-ttu-id="74d3b-129">Die **Namen** Attribut kann den Namen einer von der abstrakten Klassen finden Sie in der <xref:System.Security.Cryptography> Namespace.</span><span class="sxs-lookup"><span data-stu-id="74d3b-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="74d3b-130">Beim Aufrufen der **erstellen** Methode in einer abstrakten Kryptografieklasse, Name der abstrakten Klasse wird zum Übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="74d3b-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="74d3b-131">**CreateFromName** gibt eine Instanz des Typs, angegeben durch die **Klasse** Attribut.</span><span class="sxs-lookup"><span data-stu-id="74d3b-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="74d3b-132">Wenn die **Namen** -Attribut ist ein Kurzname wie z. B. RSA, können Sie diesen Namen beim Aufruf der **CreateFromName** Methode.</span><span class="sxs-lookup"><span data-stu-id="74d3b-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74d3b-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74d3b-133">Example</span></span>  
 <span data-ttu-id="74d3b-134">Das folgende Beispiel zeigt, wie Sie mit der  **\<NameEntry >** Element auf eine kryptografischen Klasse verweisen und die Runtime zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="74d3b-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="74d3b-135">Sie können dann an die Zeichenfolge "RSA" übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="74d3b-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74d3b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74d3b-136">See also</span></span>

- [<span data-ttu-id="74d3b-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="74d3b-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="74d3b-138">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="74d3b-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="74d3b-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="74d3b-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="74d3b-140">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="74d3b-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
