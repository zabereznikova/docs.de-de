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
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088005"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="029f0-102">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="029f0-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="029f0-103">Das Schema für Kryptografieeinstellungen enthält Elemente, die angeben, wie die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="029f0-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
<span data-ttu-id="029f0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="029f0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="029f0-105">&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="029f0-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="029f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="029f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="029f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping**](cryptonamemapping-element.md) ></span><span class="sxs-lookup"><span data-stu-id="029f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="029f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptoClasses**](cryptoclasses-element.md) ></span><span class="sxs-lookup"><span data-stu-id="029f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="029f0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClass >** ](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="029f0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>\
<span data-ttu-id="029f0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<nameEntry >** ](nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="029f0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>\
<span data-ttu-id="029f0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidmap**](oidmap-element.md) ></span><span class="sxs-lookup"><span data-stu-id="029f0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="029f0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidEntry >** ](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="029f0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>

|<span data-ttu-id="029f0-113">Element</span><span class="sxs-lookup"><span data-stu-id="029f0-113">Element</span></span>|<span data-ttu-id="029f0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="029f0-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="029f0-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="029f0-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="029f0-116">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="029f0-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="029f0-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="029f0-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="029f0-118">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="029f0-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="029f0-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="029f0-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="029f0-120">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="029f0-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="029f0-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="029f0-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="029f0-122">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="029f0-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="029f0-123"> **\<mscorlib>** -Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="029f0-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="029f0-124">Enthält das Element **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="029f0-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="029f0-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="029f0-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="029f0-126">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="029f0-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="029f0-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="029f0-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="029f0-128">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="029f0-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="029f0-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="029f0-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="029f0-130">Enthält die ASN.1-OID-Zuordnungen zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="029f0-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="029f0-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="029f0-131">See also</span></span>

- [<span data-ttu-id="029f0-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="029f0-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="029f0-133">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="029f0-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
