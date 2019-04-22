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
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206654"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="dcec5-102">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dcec5-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="dcec5-103">Stellt Methoden, die zum Generieren und Vergleichen von Schlüsseln für Anwendungsidentitäten und Verweise bereit.</span><span class="sxs-lookup"><span data-stu-id="dcec5-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dcec5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="dcec5-104">Methods</span></span>  
  
|<span data-ttu-id="dcec5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="dcec5-105">Method</span></span>|<span data-ttu-id="dcec5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dcec5-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="dcec5-107">Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) -Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="dcec5-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="dcec5-108">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit ihre jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="dcec5-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="dcec5-109">Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) -Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="dcec5-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="dcec5-110">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit ihre jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="dcec5-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="dcec5-111">Ruft einen Wert, der angibt, ob die beiden Definitionen für die angegebene Zeichenfolge gleich sind.</span><span class="sxs-lookup"><span data-stu-id="dcec5-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="dcec5-112">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit ihre jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="dcec5-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="dcec5-113">Ruft einen Wert, der angibt, ob die beiden Verweise für die angegebene Zeichenfolge gleich sind.</span><span class="sxs-lookup"><span data-stu-id="dcec5-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="dcec5-114">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit ihre jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="dcec5-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="dcec5-115">Ruft einen Schnittstellenzeiger auf einem neu generierten `IDefinitionAppId` -Instanz, die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="dcec5-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="dcec5-116">Ruft einen Schnittstellenzeiger zu einer neu erstellten `IReferenceAppId` , die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="dcec5-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="dcec5-117">Ruft eine Zeichenfolgenversion des angegebenen `IDefinitionAppId`, mit den Werten des angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="dcec5-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="dcec5-118">Ruft einen Wert, der angibt, ob das angegebene `IDefinitionAppId` und `IReferenceAppId` dieselbe Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="dcec5-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="dcec5-119">Ruft einen Wert, der angibt, ob die angegebenen parameterdefinitions-Zeichenfolge und die Verweiszeichenfolge wird die gleiche Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="dcec5-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="dcec5-120">Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IDefinitionAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="dcec5-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="dcec5-121">Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IReferenceAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="dcec5-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="dcec5-122">Ruft einen Hash-Schlüssel für den angegebenen `IDefinitionAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="dcec5-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="dcec5-123">Ruft einen Hash-Schlüssel für den angegebenen `IReferenceAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="dcec5-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="dcec5-124">Ruft eine Zeichenfolgenversion des angegebenen `IReferenceAppId`, mit den Werten des angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="dcec5-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="dcec5-125">Ruft einen Schnittstellenzeiger auf ein `IDefinitionAppId` -Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="dcec5-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="dcec5-126">Ruft einen Schnittstellenzeiger auf ein `IReferenceAppId` -Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="dcec5-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dcec5-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dcec5-127">Requirements</span></span>  
 <span data-ttu-id="dcec5-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcec5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcec5-129">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="dcec5-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="dcec5-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcec5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcec5-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcec5-131">See also</span></span>

- [<span data-ttu-id="dcec5-132">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dcec5-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
