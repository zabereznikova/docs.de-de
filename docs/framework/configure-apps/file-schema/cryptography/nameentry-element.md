---
title: '&lt;NameEntry&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1bffb72e7c68d10e2c0edd5ec3cb9bcff10cbc0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltnameentrygt-element"></a><span data-ttu-id="84e8a-102">&lt;NameEntry&gt; Element</span><span class="sxs-lookup"><span data-stu-id="84e8a-102">&lt;nameEntry&gt; Element</span></span>
<span data-ttu-id="84e8a-103">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="84e8a-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="84e8a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="84e8a-104">\<configuration></span></span>  
<span data-ttu-id="84e8a-105">\<"mscorlib" ></span><span class="sxs-lookup"><span data-stu-id="84e8a-105">\<mscorlib></span></span>  
<span data-ttu-id="84e8a-106">\<CryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="84e8a-106">\<cryptographySettings></span></span>  
<span data-ttu-id="84e8a-107">\<CryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="84e8a-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="84e8a-108">\<NameEntry ></span><span class="sxs-lookup"><span data-stu-id="84e8a-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e8a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="84e8a-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84e8a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="84e8a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="84e8a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="84e8a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84e8a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="84e8a-112">Attributes</span></span>  
  
|<span data-ttu-id="84e8a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="84e8a-113">Attribute</span></span>|<span data-ttu-id="84e8a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84e8a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84e8a-115">**name**</span><span class="sxs-lookup"><span data-stu-id="84e8a-115">**name**</span></span>|<span data-ttu-id="84e8a-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="84e8a-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="84e8a-117">Gibt den Anzeigenamen des Algorithmus, den die Kryptografieklasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="84e8a-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="84e8a-118">**class**</span><span class="sxs-lookup"><span data-stu-id="84e8a-118">**class**</span></span>|<span data-ttu-id="84e8a-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="84e8a-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="84e8a-120">Gibt den Wert für die **Namen** Attribut in der [ \<CryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="84e8a-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84e8a-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84e8a-121">Child Elements</span></span>  
 <span data-ttu-id="84e8a-122">Keine</span><span class="sxs-lookup"><span data-stu-id="84e8a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84e8a-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84e8a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="84e8a-124">Element</span><span class="sxs-lookup"><span data-stu-id="84e8a-124">Element</span></span>|<span data-ttu-id="84e8a-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84e8a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="84e8a-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="84e8a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="84e8a-127">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="84e8a-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84e8a-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84e8a-128">Remarks</span></span>  
 <span data-ttu-id="84e8a-129">Die **Namen** Attribut kann den Namen einer abstrakten Klassen der <xref:System.Security.Cryptography> Namespace.</span><span class="sxs-lookup"><span data-stu-id="84e8a-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="84e8a-130">Beim Aufrufen der **erstellen** Methode in einer abstrakten Kryptografieklasse, Name der abstrakten Klasse wird zum Übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="84e8a-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="84e8a-131">**CreateFromName** gibt eine Instanz des Typs, angegeben durch die **Klasse** Attribut.</span><span class="sxs-lookup"><span data-stu-id="84e8a-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="84e8a-132">Wenn die **Namen** -Attribut ist ein Kurzname wie z. B. RSA, können Sie diesen Namen beim Aufrufen der **CreateFromName** Methode.</span><span class="sxs-lookup"><span data-stu-id="84e8a-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84e8a-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="84e8a-133">Example</span></span>  
 <span data-ttu-id="84e8a-134">Das folgende Beispiel zeigt, wie Sie die  **\<NameEntry >** Element auf eine kryptografischen Klasse verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="84e8a-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="84e8a-135">Sie können dann die Zeichenfolge "RSA" übergeben, um die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="84e8a-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="84e8a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84e8a-136">See Also</span></span>  
 [<span data-ttu-id="84e8a-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="84e8a-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="84e8a-138">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="84e8a-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="84e8a-139">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="84e8a-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="84e8a-140">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="84e8a-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
