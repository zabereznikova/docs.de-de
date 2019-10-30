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
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127133"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="cb254-102">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb254-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="cb254-103">Stellt Methoden bereit, die Schlüssel für Anwendungs Identitäten und-Verweise generieren und vergleichen.</span><span class="sxs-lookup"><span data-stu-id="cb254-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb254-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cb254-104">Methods</span></span>  
  
|<span data-ttu-id="cb254-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cb254-105">Method</span></span>|<span data-ttu-id="cb254-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb254-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="cb254-107">Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IDefinitionAppId](idefinitionappid-interface.md) -Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="cb254-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="cb254-108">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="cb254-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="cb254-109">Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IReferenceAppId](ireferenceappid-interface.md) -Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="cb254-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="cb254-110">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="cb254-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="cb254-111">Ruft einen Wert ab, der angibt, ob die beiden angegebenen Zeichen folgen Definitionen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="cb254-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="cb254-112">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="cb254-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="cb254-113">Ruft einen Wert ab, der angibt, ob die beiden angegebenen Zeichen folgen Verweise gleich sind.</span><span class="sxs-lookup"><span data-stu-id="cb254-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="cb254-114">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="cb254-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="cb254-115">Ruft einen Schnittstellen Zeiger auf eine neu generierte `IDefinitionAppId`-Instanz ab, die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb254-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="cb254-116">Ruft einen Schnittstellen Zeiger auf ein neu erstelltes `IReferenceAppId` ab, das die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb254-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="cb254-117">Ruft mithilfe der angegebenen Flagwerte eine Zeichen folgen Version des angegebenen `IDefinitionAppId`ab.</span><span class="sxs-lookup"><span data-stu-id="cb254-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="cb254-118">Ruft einen Wert ab, der angibt, ob die angegebene `IDefinitionAppId` und `IReferenceAppId` die gleiche Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="cb254-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="cb254-119">Ruft einen Wert ab, der angibt, ob die angegebene Definitions Zeichenfolge und die Verweis Zeichenfolge dieselbe Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="cb254-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="cb254-120">Ruft einen Zeichen folgen Schlüssel ab, der die angegebene `IDefinitionAppId` Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb254-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="cb254-121">Ruft einen Zeichen folgen Schlüssel ab, der die angegebene `IReferenceAppId` Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb254-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="cb254-122">Ruft einen Hashwert für die angegebene `IDefinitionAppId` Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="cb254-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="cb254-123">Ruft einen Hashwert für die angegebene `IReferenceAppId` Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="cb254-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="cb254-124">Ruft mithilfe der angegebenen Flagwerte eine Zeichen folgen Version des angegebenen `IReferenceAppId`ab.</span><span class="sxs-lookup"><span data-stu-id="cb254-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="cb254-125">Ruft einen Schnittstellen Zeiger auf eine `IDefinitionAppId`-Instanz ab, die die Assembly darstellt, auf die durch den angegebenen Zeichen folgen Schlüssel verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cb254-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="cb254-126">Ruft einen Schnittstellen Zeiger auf eine `IReferenceAppId`-Instanz ab, die die Assembly darstellt, auf die durch den angegebenen Zeichen folgen Schlüssel verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cb254-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb254-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb254-127">Requirements</span></span>  
 <span data-ttu-id="cb254-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb254-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb254-129">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="cb254-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="cb254-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb254-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb254-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb254-131">See also</span></span>

- [<span data-ttu-id="cb254-132">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cb254-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
