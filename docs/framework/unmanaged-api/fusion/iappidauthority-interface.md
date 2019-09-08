---
title: IAppIdAuthority-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91ab2f71e7fb74f8e0e517b566d46d61c316ebe2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796838"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="02cd4-102">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02cd4-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="02cd4-103">Stellt Methoden bereit, die Schlüssel für Anwendungs Identitäten und-Verweise generieren und vergleichen.</span><span class="sxs-lookup"><span data-stu-id="02cd4-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02cd4-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="02cd4-104">Methods</span></span>  
  
|<span data-ttu-id="02cd4-105">Methode</span><span class="sxs-lookup"><span data-stu-id="02cd4-105">Method</span></span>|<span data-ttu-id="02cd4-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02cd4-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="02cd4-107">Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IDefinitionAppId](idefinitionappid-interface.md) -Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="02cd4-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="02cd4-108">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="02cd4-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="02cd4-109">Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IReferenceAppId](ireferenceappid-interface.md) -Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="02cd4-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="02cd4-110">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="02cd4-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="02cd4-111">Ruft einen Wert ab, der angibt, ob die beiden angegebenen Zeichen folgen Definitionen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="02cd4-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="02cd4-112">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="02cd4-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="02cd4-113">Ruft einen Wert ab, der angibt, ob die beiden angegebenen Zeichen folgen Verweise gleich sind.</span><span class="sxs-lookup"><span data-stu-id="02cd4-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="02cd4-114">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="02cd4-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="02cd4-115">Ruft einen Schnittstellen Zeiger auf eine neu generierte `IDefinitionAppId` -Instanz ab, die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="02cd4-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="02cd4-116">Ruft einen Schnittstellen Zeiger auf eine neu erstellte `IReferenceAppId` ab, die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="02cd4-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="02cd4-117">Ruft mithilfe der angegebenen Flagwerte eine `IDefinitionAppId`Zeichen folgen Version des angegebenen ab.</span><span class="sxs-lookup"><span data-stu-id="02cd4-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="02cd4-118">Ruft einen Wert ab, der angibt, `IDefinitionAppId` ob `IReferenceAppId` der angegebene und die gleiche Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="02cd4-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="02cd4-119">Ruft einen Wert ab, der angibt, ob die angegebene Definitions Zeichenfolge und die Verweis Zeichenfolge dieselbe Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="02cd4-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="02cd4-120">Ruft einen Zeichen folgen Schlüssel ab, der `IDefinitionAppId` die angegebene-Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="02cd4-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="02cd4-121">Ruft einen Zeichen folgen Schlüssel ab, der `IReferenceAppId` die angegebene-Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="02cd4-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="02cd4-122">Ruft einen Hashwert für die angegebene `IDefinitionAppId` -Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="02cd4-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="02cd4-123">Ruft einen Hashwert für die angegebene `IReferenceAppId` -Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="02cd4-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="02cd4-124">Ruft mithilfe der angegebenen Flagwerte eine `IReferenceAppId`Zeichen folgen Version des angegebenen ab.</span><span class="sxs-lookup"><span data-stu-id="02cd4-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="02cd4-125">Ruft einen Schnittstellen Zeiger auf eine `IDefinitionAppId` -Instanz ab, die die Assembly darstellt, auf die vom angegebenen Zeichen folgen Schlüssel verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="02cd4-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="02cd4-126">Ruft einen Schnittstellen Zeiger auf eine `IReferenceAppId` -Instanz ab, die die Assembly darstellt, auf die vom angegebenen Zeichen folgen Schlüssel verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="02cd4-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02cd4-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02cd4-127">Requirements</span></span>  
 <span data-ttu-id="02cd4-128">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02cd4-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02cd4-129">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="02cd4-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="02cd4-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02cd4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02cd4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02cd4-131">See also</span></span>

- [<span data-ttu-id="02cd4-132">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="02cd4-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
