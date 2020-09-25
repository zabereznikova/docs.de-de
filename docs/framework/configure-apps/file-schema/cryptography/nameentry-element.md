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
ms.openlocfilehash: 4341b1fcd3762e5aa55f0ba988f7f49d4b5cacd6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201771"
---
# <a name="nameentry-element"></a><span data-ttu-id="54cdb-102">\<nameEntry>-Element</span><span class="sxs-lookup"><span data-stu-id="54cdb-102">\<nameEntry> Element</span></span>

<span data-ttu-id="54cdb-103">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="54cdb-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**  
  
## <a name="syntax"></a><span data-ttu-id="54cdb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="54cdb-104">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54cdb-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="54cdb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="54cdb-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="54cdb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54cdb-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="54cdb-107">Attributes</span></span>  
  
|<span data-ttu-id="54cdb-108">attribute</span><span class="sxs-lookup"><span data-stu-id="54cdb-108">Attribute</span></span>|<span data-ttu-id="54cdb-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54cdb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54cdb-110">**name**</span><span class="sxs-lookup"><span data-stu-id="54cdb-110">**name**</span></span>|<span data-ttu-id="54cdb-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="54cdb-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="54cdb-112">Gibt den anzeigen amen des von der Kryptografieklasse implementierten Algorithmus an.</span><span class="sxs-lookup"><span data-stu-id="54cdb-112">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="54cdb-113">**class**</span><span class="sxs-lookup"><span data-stu-id="54cdb-113">**class**</span></span>|<span data-ttu-id="54cdb-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="54cdb-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="54cdb-115">Gibt den Wert für das **Name** -Attribut im- [\<cryptoClass>](cryptoclass-element.md) Element an.</span><span class="sxs-lookup"><span data-stu-id="54cdb-115">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54cdb-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54cdb-116">Child Elements</span></span>  

 <span data-ttu-id="54cdb-117">Keine</span><span class="sxs-lookup"><span data-stu-id="54cdb-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54cdb-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54cdb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="54cdb-119">Element</span><span class="sxs-lookup"><span data-stu-id="54cdb-119">Element</span></span>|<span data-ttu-id="54cdb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54cdb-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="54cdb-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="54cdb-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="54cdb-122">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="54cdb-122">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54cdb-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="54cdb-123">Remarks</span></span>  

 <span data-ttu-id="54cdb-124">Das **Name** -Attribut kann der Name einer der abstrakten Klassen sein, die im- <xref:System.Security.Cryptography> Namespace gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="54cdb-124">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="54cdb-125">Wenn Sie die **Create** -Methode für eine abstrakte Kryptografieklasse aufzurufen, wird der abstrakte Klassenname an die-Methode weitergegeben <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> .</span><span class="sxs-lookup"><span data-stu-id="54cdb-125">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="54cdb-126">" **Kreatefromname** " gibt eine Instanz des Typs zurück, der durch das **Class** -Attribut angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="54cdb-126">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="54cdb-127">Wenn das **Name** -Attribut ein Kurzname ist (z. b. RSA), können Sie diesen Namen verwenden, wenn Sie die **CreateFromName** -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="54cdb-127">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54cdb-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="54cdb-128">Example</span></span>  

 <span data-ttu-id="54cdb-129">Im folgenden Beispiel wird gezeigt, wie das **\<nameEntry>** -Element verwendet wird, um auf eine Kryptografieklasse zu verweisen und die Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="54cdb-129">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="54cdb-130">Anschließend können Sie die Zeichenfolge "RSA" an die <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode übergeben und die- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> Methode verwenden, um ein-Objekt zurückzugeben `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="54cdb-130">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54cdb-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54cdb-131">See also</span></span>

- [<span data-ttu-id="54cdb-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="54cdb-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="54cdb-133">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="54cdb-133">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="54cdb-134">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="54cdb-134">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="54cdb-135">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="54cdb-135">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
