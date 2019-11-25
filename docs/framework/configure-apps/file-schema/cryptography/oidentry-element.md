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
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088553"
---
# <a name="oidentry-element"></a><span data-ttu-id="2e97d-102">\<oidEntry >-Element</span><span class="sxs-lookup"><span data-stu-id="2e97d-102">\<oidEntry> Element</span></span>
<span data-ttu-id="2e97d-103">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="2e97d-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

<span data-ttu-id="2e97d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e97d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e97d-105">&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2e97d-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="2e97d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e97d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="2e97d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidmap**](oidmap-element.md) ></span><span class="sxs-lookup"><span data-stu-id="2e97d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="2e97d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<oidEntry >**</span><span class="sxs-lookup"><span data-stu-id="2e97d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2e97d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e97d-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e97d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2e97d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2e97d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e97d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e97d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2e97d-112">Attributes</span></span>  
  
|<span data-ttu-id="2e97d-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2e97d-113">Attribute</span></span>|<span data-ttu-id="2e97d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e97d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e97d-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="2e97d-115">**OID**</span></span>|<span data-ttu-id="2e97d-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2e97d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="2e97d-117">Gibt die ASN. 1-OID an, die dem von der Klasse implementierten Algorithmus entspricht.</span><span class="sxs-lookup"><span data-stu-id="2e97d-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="2e97d-118">**name**</span><span class="sxs-lookup"><span data-stu-id="2e97d-118">**name**</span></span>|<span data-ttu-id="2e97d-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2e97d-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="2e97d-120">Gibt den Wert für das **Name** -Attribut im [\<nameEntry >](nameentry-element.md) -Tags an.</span><span class="sxs-lookup"><span data-stu-id="2e97d-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e97d-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e97d-121">Child Elements</span></span>  
 <span data-ttu-id="2e97d-122">Keine</span><span class="sxs-lookup"><span data-stu-id="2e97d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e97d-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e97d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2e97d-124">Element</span><span class="sxs-lookup"><span data-stu-id="2e97d-124">Element</span></span>|<span data-ttu-id="2e97d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e97d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2e97d-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2e97d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="2e97d-127">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="2e97d-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="2e97d-128">Enthält das `cryptographySettings` Element.</span><span class="sxs-lookup"><span data-stu-id="2e97d-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="2e97d-129">Enthält ASN. 1 objektbezeichnermappings (OID) zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="2e97d-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e97d-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e97d-130">Remarks</span></span>  
 <span data-ttu-id="2e97d-131">ASN. 1-Objekt Bezeichner erkennen Algorithmen in einigen kryptografieformaten.</span><span class="sxs-lookup"><span data-stu-id="2e97d-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="2e97d-132">Ordnen Sie den anzeigen Amen für die Algorithmen, die Sie identifizieren möchten, Objekt Bezeichner zu.</span><span class="sxs-lookup"><span data-stu-id="2e97d-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e97d-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e97d-133">Example</span></span>  
 <span data-ttu-id="2e97d-134">Im folgenden Beispiel wird gezeigt, wie das **\<oidEntry >** -Element verwendet wird, um einer Implementierung dieses Hash Algorithmus einen Objekt Bezeichner für den RIPEMD-160-Hash Algorithmus zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="2e97d-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2e97d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e97d-135">See also</span></span>

- [<span data-ttu-id="2e97d-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2e97d-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2e97d-137">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2e97d-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2e97d-138">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="2e97d-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="2e97d-139">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="2e97d-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="2e97d-140">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="2e97d-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
