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
ms.openlocfilehash: 819afec2c448e5f396ab54e2dde00c01da310b12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433749"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="4f062-102">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f062-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="4f062-103">Stellt Methoden, die zum Generieren und Vergleichen von Schlüsseln für Anwendungsidentitäten und Verweise.</span><span class="sxs-lookup"><span data-stu-id="4f062-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f062-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4f062-104">Methods</span></span>  
  
|<span data-ttu-id="4f062-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4f062-105">Method</span></span>|<span data-ttu-id="4f062-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f062-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="4f062-107">Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="4f062-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="4f062-108">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f062-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="4f062-109">Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="4f062-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="4f062-110">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f062-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="4f062-111">Ruft einen Wert, der angibt, ob die beiden Definitionen für die angegebene Zeichenfolge gleich sind.</span><span class="sxs-lookup"><span data-stu-id="4f062-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="4f062-112">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f062-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="4f062-113">Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolgenverweise gleich sind.</span><span class="sxs-lookup"><span data-stu-id="4f062-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="4f062-114">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f062-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="4f062-115">Ruft einen Schnittstellenzeiger auf eine neu generierte `IDefinitionAppId` Instanz, die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="4f062-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="4f062-116">Ruft einen Schnittstellenzeiger auf eine neu erstellte `IReferenceAppId` , die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="4f062-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="4f062-117">Ruft eine Zeichenfolgenversion des angegebenen `IDefinitionAppId`, mit der angegebenen Flagwerte.</span><span class="sxs-lookup"><span data-stu-id="4f062-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="4f062-118">Ruft einen Wert, der angibt, ob das angegebene `IDefinitionAppId` und `IReferenceAppId` dieselbe Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="4f062-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="4f062-119">Ruft einen Wert, der angibt, ob die angegebene parameterdefinitions-Zeichenfolge und der Verweiszeichenfolge dieselbe Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="4f062-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="4f062-120">Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IDefinitionAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="4f062-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="4f062-121">Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IReferenceAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="4f062-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="4f062-122">Ruft einen Hash-Schlüssel für den angegebenen `IDefinitionAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="4f062-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="4f062-123">Ruft einen Hash-Schlüssel für den angegebenen `IReferenceAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="4f062-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="4f062-124">Ruft eine Zeichenfolgenversion des angegebenen `IReferenceAppId`, mit der angegebenen Flagwerte.</span><span class="sxs-lookup"><span data-stu-id="4f062-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="4f062-125">Ruft einen Schnittstellenzeiger auf eine `IDefinitionAppId` Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="4f062-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="4f062-126">Ruft einen Schnittstellenzeiger auf eine `IReferenceAppId` Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="4f062-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f062-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f062-127">Requirements</span></span>  
 <span data-ttu-id="4f062-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f062-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f062-129">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="4f062-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4f062-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f062-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f062-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f062-131">See Also</span></span>  
 [<span data-ttu-id="4f062-132">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f062-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
