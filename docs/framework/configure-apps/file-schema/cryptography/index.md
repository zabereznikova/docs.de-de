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
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927633"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="eada9-102">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="eada9-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="eada9-103">Das Schema für Kryptografieeinstellungen enthält Elemente, die angeben, wie die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="eada9-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="eada9-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="eada9-104">**\<configuration>**</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="eada9-105"> **\<mscorlib>** </span><span class="sxs-lookup"><span data-stu-id="eada9-105">**\<mscorlib>**</span></span>](mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="eada9-106"> **\<cryptographySettings>** </span><span class="sxs-lookup"><span data-stu-id="eada9-106">**\<cryptographySettings>**</span></span>](cryptographysettings-element.md)  
  
 [<span data-ttu-id="eada9-107"> **\<cryptoNameMapping>** </span><span class="sxs-lookup"><span data-stu-id="eada9-107">**\<cryptoNameMapping>**</span></span>](cryptonamemapping-element.md)  
  
 [<span data-ttu-id="eada9-108"> **\<cryptoClasses>** </span><span class="sxs-lookup"><span data-stu-id="eada9-108">**\<cryptoClasses>**</span></span>](cryptoclasses-element.md)  
  
 [<span data-ttu-id="eada9-109"> **\<cryptoClass>** </span><span class="sxs-lookup"><span data-stu-id="eada9-109">**\<cryptoClass>**</span></span>](cryptoclass-element.md)  
  
 [<span data-ttu-id="eada9-110"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="eada9-110">**\<nameEntry>**</span></span>](nameentry-element.md)  
  
 [<span data-ttu-id="eada9-111"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="eada9-111">**\<oidMap>**</span></span>](oidmap-element.md)  
  
 [<span data-ttu-id="eada9-112"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="eada9-112">**\<oidEntry>**</span></span>](oidentry-element.md)  
  
|<span data-ttu-id="eada9-113">Element</span><span class="sxs-lookup"><span data-stu-id="eada9-113">Element</span></span>|<span data-ttu-id="eada9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eada9-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eada9-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="eada9-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="eada9-116">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="eada9-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="eada9-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="eada9-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="eada9-118">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="eada9-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="eada9-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="eada9-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="eada9-120">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="eada9-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="eada9-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="eada9-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="eada9-122">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="eada9-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="eada9-123"> **\<mscorlib>** -Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="eada9-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="eada9-124">Enthält das Element **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="eada9-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="eada9-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="eada9-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="eada9-126">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="eada9-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="eada9-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="eada9-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="eada9-128">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="eada9-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="eada9-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="eada9-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="eada9-130">Enthält die ASN.1-OID-Zuordnungen zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="eada9-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eada9-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eada9-131">See also</span></span>

- [<span data-ttu-id="eada9-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="eada9-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="eada9-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="eada9-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
