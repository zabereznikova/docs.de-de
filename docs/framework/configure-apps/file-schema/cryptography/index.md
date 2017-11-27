---
title: "Schema für Kryptografieeinstellungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c7d1e193236528c96e8253668c742883090ae188
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="415d7-102">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="415d7-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="415d7-103">Das Schema für Kryptografieeinstellungen enthält Elemente, die angeben, wie die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="415d7-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="415d7-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="415d7-104">**\<configuration>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="415d7-105">**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="415d7-105">**\<mscorlib>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="415d7-106">**\<cryptographySettings>**</span><span class="sxs-lookup"><span data-stu-id="415d7-106">**\<cryptographySettings>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [<span data-ttu-id="415d7-107">**\<cryptoNameMapping>**</span><span class="sxs-lookup"><span data-stu-id="415d7-107">**\<cryptoNameMapping>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [<span data-ttu-id="415d7-108">**\<cryptoClasses>**</span><span class="sxs-lookup"><span data-stu-id="415d7-108">**\<cryptoClasses>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [<span data-ttu-id="415d7-109">**\<cryptoClass>**</span><span class="sxs-lookup"><span data-stu-id="415d7-109">**\<cryptoClass>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [<span data-ttu-id="415d7-110">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="415d7-110">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [<span data-ttu-id="415d7-111">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="415d7-111">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [<span data-ttu-id="415d7-112">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="415d7-112">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|<span data-ttu-id="415d7-113">Element</span><span class="sxs-lookup"><span data-stu-id="415d7-113">Element</span></span>|<span data-ttu-id="415d7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="415d7-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="415d7-115">**\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="415d7-115">**\<cryptoClasses**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|<span data-ttu-id="415d7-116">Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="415d7-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="415d7-117">**\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="415d7-117">**\<cryptoClass**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="415d7-118">Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="415d7-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="415d7-119">**\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="415d7-119">**\<cryptographySettings**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|<span data-ttu-id="415d7-120">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="415d7-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="415d7-121">**\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="415d7-121">**\<cryptoNameMapping**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="415d7-122">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="415d7-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="415d7-123">**\<mscorlib>**-Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="415d7-123">**\<mscorlib>** element for cryptography settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="415d7-124">Enthält das Element **\<cryptographySettings>**.</span><span class="sxs-lookup"><span data-stu-id="415d7-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="415d7-125">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="415d7-125">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|<span data-ttu-id="415d7-126">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="415d7-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="415d7-127">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="415d7-127">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="415d7-128">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="415d7-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="415d7-129">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="415d7-129">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="415d7-130">Enthält die ASN.1-OID-Zuordnungen zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="415d7-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="415d7-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="415d7-131">See Also</span></span>  
 [<span data-ttu-id="415d7-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="415d7-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="415d7-133">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="415d7-133">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
