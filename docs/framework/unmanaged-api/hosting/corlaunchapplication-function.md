---
title: CorLaunchApplication-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type: COM
f1_keywords: CorLaunchApplication
helpviewer_keywords: CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf4392f7b30a5faa1cb01e24f9262260d9c6e93a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="072bb-102">CorLaunchApplication-Funktion</span><span class="sxs-lookup"><span data-stu-id="072bb-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="072bb-103">Startet die Anwendung im angegebenen Netzwerkpfad, wobei die angegebenen Manifeste und sonstigen Anwendungsdaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="072bb-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="072bb-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="072bb-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="072bb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="072bb-105">Syntax</span></span>  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="072bb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="072bb-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="072bb-107">[in] Der Wert der [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) -Enumeration, der den Typ des Hosts gibt an, die die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="072bb-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="072bb-108">[in] Der vollständige Name der Anwendung, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="072bb-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="072bb-109">[in] Die Anzahl der Manifestdatei Pfade für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="072bb-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="072bb-110">[in] Ein Array von Zeichenfolgen, von denen jedes einen Pfad zu einem Manifest für die Anwendung angibt, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="072bb-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="072bb-111">[in] Die Anzahl der Aktivierung der Datenelemente für die Anwendung, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="072bb-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="072bb-112">[in] Ein Array von Zeichenfolgen, von denen jeder ein Aktivierungsdatenelement für die Anwendung ist, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="072bb-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="072bb-113">[out] Ein Zeiger auf Informationen über den Prozess, in dem die Anwendung geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="072bb-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="072bb-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="072bb-114">Requirements</span></span>  
 <span data-ttu-id="072bb-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="072bb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="072bb-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="072bb-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="072bb-117">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="072bb-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="072bb-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="072bb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072bb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="072bb-119">See Also</span></span>  
 [<span data-ttu-id="072bb-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="072bb-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
