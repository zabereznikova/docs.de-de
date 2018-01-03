---
title: IAppIdAuthority-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppIdAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IAppIdAuthority
helpviewer_keywords: IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c51aac28864cba5f538f7829ba4112b141c9a3c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="668a3-102">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="668a3-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="668a3-103">Stellt Methoden, die zum Generieren und Vergleichen von Schlüsseln für Anwendungsidentitäten und Verweise.</span><span class="sxs-lookup"><span data-stu-id="668a3-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="668a3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="668a3-104">Methods</span></span>  
  
|<span data-ttu-id="668a3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="668a3-105">Method</span></span>|<span data-ttu-id="668a3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="668a3-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="668a3-107">Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="668a3-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="668a3-108">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="668a3-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="668a3-109">Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="668a3-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="668a3-110">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="668a3-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="668a3-111">Ruft einen Wert, der angibt, ob die beiden Definitionen für die angegebene Zeichenfolge gleich sind.</span><span class="sxs-lookup"><span data-stu-id="668a3-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="668a3-112">Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="668a3-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="668a3-113">Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolgenverweise gleich sind.</span><span class="sxs-lookup"><span data-stu-id="668a3-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="668a3-114">Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.</span><span class="sxs-lookup"><span data-stu-id="668a3-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="668a3-115">Ruft einen Schnittstellenzeiger auf eine neu generierte `IDefinitionAppId` Instanz, die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="668a3-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="668a3-116">Ruft einen Schnittstellenzeiger auf eine neu erstellte `IReferenceAppId` , die die Assembly im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="668a3-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="668a3-117">Ruft eine Zeichenfolgenversion des angegebenen `IDefinitionAppId`, mit der angegebenen Flagwerte.</span><span class="sxs-lookup"><span data-stu-id="668a3-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="668a3-118">Ruft einen Wert, der angibt, ob das angegebene `IDefinitionAppId` und `IReferenceAppId` dieselbe Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="668a3-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="668a3-119">Ruft einen Wert, der angibt, ob die angegebene parameterdefinitions-Zeichenfolge und der Verweiszeichenfolge dieselbe Assembly darstellen.</span><span class="sxs-lookup"><span data-stu-id="668a3-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="668a3-120">Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IDefinitionAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="668a3-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="668a3-121">Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IReferenceAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="668a3-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="668a3-122">Ruft einen Hash-Schlüssel für den angegebenen `IDefinitionAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="668a3-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="668a3-123">Ruft einen Hash-Schlüssel für den angegebenen `IReferenceAppId` Instanz.</span><span class="sxs-lookup"><span data-stu-id="668a3-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="668a3-124">Ruft eine Zeichenfolgenversion des angegebenen `IReferenceAppId`, mit der angegebenen Flagwerte.</span><span class="sxs-lookup"><span data-stu-id="668a3-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="668a3-125">Ruft einen Schnittstellenzeiger auf eine `IDefinitionAppId` Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="668a3-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="668a3-126">Ruft einen Schnittstellenzeiger auf eine `IReferenceAppId` Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="668a3-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="668a3-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="668a3-127">Requirements</span></span>  
 <span data-ttu-id="668a3-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="668a3-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="668a3-129">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="668a3-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="668a3-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="668a3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668a3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="668a3-131">See Also</span></span>  
 [<span data-ttu-id="668a3-132">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="668a3-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
