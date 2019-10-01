---
title: Schema für Kryptografieeinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: 474c3274bfba6803ebb17289f138251d755250e4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699801"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="4416f-102">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="4416f-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="4416f-103">Das Schema für Kryptografieeinstellungen enthält Elemente, die angeben, wie die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="4416f-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[<span data-ttu-id="4416f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4416f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="4416f-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4416f-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="4416f-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographysettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="4416f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="4416f-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<cryptonamemapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="4416f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="4416f-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0cryptoclasses >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="4416f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>  
<span data-ttu-id="4416f-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9[ **&nbsp;2cryptoclass >** ](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="4416f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>  
<span data-ttu-id="4416f-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0nameentry >** ](nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="4416f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>  
<span data-ttu-id="4416f-111">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<oidmap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="4416f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>  
<span data-ttu-id="4416f-112">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6[ **\<oidentry >** ](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="4416f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>  
  
|<span data-ttu-id="4416f-113">Element</span><span class="sxs-lookup"><span data-stu-id="4416f-113">Element</span></span>|<span data-ttu-id="4416f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4416f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4416f-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="4416f-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="4416f-116">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4416f-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="4416f-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="4416f-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="4416f-118">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4416f-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="4416f-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="4416f-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="4416f-120">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4416f-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="4416f-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="4416f-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="4416f-122">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="4416f-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="4416f-123"> **\<mscorlib>** -Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="4416f-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="4416f-124">Enthält das Element **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="4416f-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="4416f-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="4416f-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="4416f-126">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="4416f-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="4416f-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="4416f-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="4416f-128">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="4416f-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="4416f-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="4416f-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="4416f-130">Enthält die ASN.1-OID-Zuordnungen zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="4416f-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4416f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4416f-131">See also</span></span>

- [<span data-ttu-id="4416f-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="4416f-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4416f-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4416f-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
