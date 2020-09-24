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
ms.openlocfilehash: 0215851f83a13ee48547144f08c5c693ec2d90bf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149529"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="b4c80-102">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="b4c80-102">Cryptography Settings Schema</span></span>

<span data-ttu-id="b4c80-103">Das Schema für Kryptografieeinstellungen enthält Elemente, die angeben, wie die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="b4c80-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|<span data-ttu-id="b4c80-104">Element</span><span class="sxs-lookup"><span data-stu-id="b4c80-104">Element</span></span>|<span data-ttu-id="b4c80-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4c80-105">Description</span></span>|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|<span data-ttu-id="b4c80-106">Enthält eine Liste von Kryptografieklassen, die eine Zuordnung zu einem anzeigen Amen im- **\<nameEntry>** Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b4c80-106">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptoClass**>](cryptoclass-element.md)|<span data-ttu-id="b4c80-107">Enthält eine Kryptografieklasse, die eine Zuordnung zu einem anzeigen Amen im- **\<nameEntry>** Element aufweist.</span><span class="sxs-lookup"><span data-stu-id="b4c80-107">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|<span data-ttu-id="b4c80-108">Enthält Kryptografieeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="b4c80-108">Contains cryptography settings.</span></span>|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|<span data-ttu-id="b4c80-109">Enthält die Zuordnung von Klassen zu den Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="b4c80-109">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="b4c80-110">**\<mscorlib>** -Element für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="b4c80-110">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="b4c80-111">Enthält das- **\<cryptographySettings>** Element.</span><span class="sxs-lookup"><span data-stu-id="b4c80-111">Contains the **\<cryptographySettings>** element.</span></span>|  
|[**\<nameEntry>**](nameentry-element.md)|<span data-ttu-id="b4c80-112">Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="b4c80-112">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[**\<oidEntry>**](oidentry-element.md)|<span data-ttu-id="b4c80-113">Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.</span><span class="sxs-lookup"><span data-stu-id="b4c80-113">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[**\<oidMap>**](oidmap-element.md)|<span data-ttu-id="b4c80-114">Enthält die ASN.1-OID-Zuordnungen zu Klassen.</span><span class="sxs-lookup"><span data-stu-id="b4c80-114">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4c80-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4c80-115">See also</span></span>

- [<span data-ttu-id="b4c80-116">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b4c80-116">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b4c80-117">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="b4c80-117">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
