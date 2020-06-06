---
title: <oidEntry>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 4564cf59e3b6cfbdcd9dca06cd0f966d524834de
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088553"
---
# <a name="oidentry-element"></a><span data-ttu-id="f7c55-102">\<oidEntry>-Element</span><span class="sxs-lookup"><span data-stu-id="f7c55-102">\<oidEntry> Element</span></span>
<span data-ttu-id="f7c55-103">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="f7c55-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a><span data-ttu-id="f7c55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7c55-104">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7c55-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f7c55-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f7c55-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7c55-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7c55-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="f7c55-107">Attributes</span></span>  
  
|<span data-ttu-id="f7c55-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f7c55-108">Attribute</span></span>|<span data-ttu-id="f7c55-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f7c55-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7c55-110">**OID**</span><span class="sxs-lookup"><span data-stu-id="f7c55-110">**OID**</span></span>|<span data-ttu-id="f7c55-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f7c55-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="f7c55-112">Gibt die ASN. 1-OID an, die dem von der Klasse implementierten Algorithmus entspricht.</span><span class="sxs-lookup"><span data-stu-id="f7c55-112">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="f7c55-113">**name**</span><span class="sxs-lookup"><span data-stu-id="f7c55-113">**name**</span></span>|<span data-ttu-id="f7c55-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f7c55-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="f7c55-115">Gibt den Wert für das **Name** -Attribut im- [\<nameEntry>](nameentry-element.md) Tag an.</span><span class="sxs-lookup"><span data-stu-id="f7c55-115">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7c55-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7c55-116">Child Elements</span></span>  
 <span data-ttu-id="f7c55-117">Keine</span><span class="sxs-lookup"><span data-stu-id="f7c55-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7c55-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7c55-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f7c55-119">Element</span><span class="sxs-lookup"><span data-stu-id="f7c55-119">Element</span></span>|<span data-ttu-id="f7c55-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7c55-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f7c55-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f7c55-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f7c55-122">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f7c55-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="f7c55-123">Enthält das- `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="f7c55-123">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="f7c55-124">Enthält ASN. 1 objektbezeichnermappings (OID) zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="f7c55-124">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7c55-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f7c55-125">Remarks</span></span>  
 <span data-ttu-id="f7c55-126">ASN. 1-Objekt Bezeichner erkennen Algorithmen in einigen kryptografieformaten.</span><span class="sxs-lookup"><span data-stu-id="f7c55-126">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="f7c55-127">Ordnen Sie den anzeigen Amen für die Algorithmen, die Sie identifizieren möchten, Objekt Bezeichner zu.</span><span class="sxs-lookup"><span data-stu-id="f7c55-127">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7c55-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7c55-128">Example</span></span>  
 <span data-ttu-id="f7c55-129">Im folgenden Beispiel wird gezeigt, wie mit dem **\<oidEntry>** -Element ein Objekt Bezeichner für den RIPEMD-160-Hash Algorithmus einer Implementierung dieses Hash Algorithmus zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="f7c55-129">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7c55-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7c55-130">See also</span></span>

- [<span data-ttu-id="f7c55-131">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f7c55-131">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f7c55-132">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="f7c55-132">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f7c55-133">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="f7c55-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="f7c55-134">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="f7c55-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="f7c55-135">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="f7c55-135">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
