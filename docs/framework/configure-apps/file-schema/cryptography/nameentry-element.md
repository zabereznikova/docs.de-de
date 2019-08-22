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
ms.openlocfilehash: 9270552245b3867f0f09741ded3f9da6a8b6c135
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664272"
---
# <a name="nameentry-element"></a><span data-ttu-id="e5517-102">\<nameEntry-> Element</span><span class="sxs-lookup"><span data-stu-id="e5517-102">\<nameEntry> Element</span></span>
<span data-ttu-id="e5517-103">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e5517-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="e5517-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e5517-104">\<configuration></span></span>  
<span data-ttu-id="e5517-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="e5517-105">\<mscorlib></span></span>  
<span data-ttu-id="e5517-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="e5517-106">\<cryptographySettings></span></span>  
<span data-ttu-id="e5517-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="e5517-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="e5517-108">\<nameEntry></span><span class="sxs-lookup"><span data-stu-id="e5517-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5517-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5517-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5517-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e5517-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e5517-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5517-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5517-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e5517-112">Attributes</span></span>  
  
|<span data-ttu-id="e5517-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e5517-113">Attribute</span></span>|<span data-ttu-id="e5517-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5517-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5517-115">**name**</span><span class="sxs-lookup"><span data-stu-id="e5517-115">**name**</span></span>|<span data-ttu-id="e5517-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e5517-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e5517-117">Gibt den anzeigen amen des von der Kryptografieklasse implementierten Algorithmus an.</span><span class="sxs-lookup"><span data-stu-id="e5517-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="e5517-118">**class**</span><span class="sxs-lookup"><span data-stu-id="e5517-118">**class**</span></span>|<span data-ttu-id="e5517-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e5517-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="e5517-120">Gibt den Wert für das **Name** -Attribut im [ \<cryptoClass->](cryptoclass-element.md) Element an.</span><span class="sxs-lookup"><span data-stu-id="e5517-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5517-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e5517-121">Child Elements</span></span>  
 <span data-ttu-id="e5517-122">Keine</span><span class="sxs-lookup"><span data-stu-id="e5517-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5517-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e5517-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e5517-124">Element</span><span class="sxs-lookup"><span data-stu-id="e5517-124">Element</span></span>|<span data-ttu-id="e5517-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5517-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e5517-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e5517-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="e5517-127">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="e5517-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5517-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5517-128">Remarks</span></span>  
 <span data-ttu-id="e5517-129">Das **Name** -Attribut kann der Name einer der abstrakten Klassen sein, die im <xref:System.Security.Cryptography> -Namespace gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="e5517-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="e5517-130">Wenn Sie die **Create** -Methode für eine abstrakte Kryptografieklasse aufzurufen, wird der abstrakte Klassenname <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> an die-Methode weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="e5517-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="e5517-131">" **Kreatefromname** " gibt eine Instanz des Typs zurück, der durch das **Class** -Attribut angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e5517-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="e5517-132">Wenn das **Name** -Attribut ein Kurzname ist (z. b. RSA), können Sie diesen Namen verwenden, wenn Sie die **CreateFromName** -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e5517-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5517-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5517-133">Example</span></span>  
 <span data-ttu-id="e5517-134">Im folgenden Beispiel wird gezeigt, wie das  **\<nameEntry >** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e5517-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e5517-135">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> die-Methode verwenden `MyCryptoRSAClass` , um ein-Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e5517-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5517-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5517-136">See also</span></span>

- [<span data-ttu-id="e5517-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e5517-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e5517-138">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e5517-138">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e5517-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e5517-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="e5517-140">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="e5517-140">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
