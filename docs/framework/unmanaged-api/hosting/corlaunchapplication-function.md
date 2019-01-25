---
title: CorLaunchApplication-Funktion
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f2a05009caed7bef6da9edee57a4a54b876b18f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580992"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="c4888-102">CorLaunchApplication-Funktion</span><span class="sxs-lookup"><span data-stu-id="c4888-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="c4888-103">Startet die Anwendung im angegebenen Netzwerkpfad, wobei die angegebenen Manifeste und sonstigen Anwendungsdaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4888-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="c4888-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="c4888-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4888-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4888-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="c4888-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4888-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="c4888-107">[in] Der Wert der [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) -Enumeration, der den Typ des Hosts gibt an, die die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c4888-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="c4888-108">[in] Der vollständige Name der Anwendung, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c4888-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="c4888-109">[in] Die Anzahl der Manifestspfade für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c4888-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="c4888-110">[in] Ein Array von Zeichenfolgen, von denen jede einen Pfad zu einem Anwendungsmanifest für die Anwendung angibt, das gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c4888-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="c4888-111">[in] Die Anzahl der Aktivierung von Datenelementen für die Anwendung, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c4888-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="c4888-112">[in] Ein Array von Zeichenfolgen, von denen jede eine Aktivierung-Datenelement für die Anwendung ist, das gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c4888-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="c4888-113">[out] Ein Zeiger auf die Informationen über den Prozess, in dem die Anwendung geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="c4888-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4888-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4888-114">Requirements</span></span>  
 <span data-ttu-id="c4888-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4888-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4888-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4888-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4888-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4888-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4888-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4888-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4888-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4888-119">See also</span></span>
- [<span data-ttu-id="c4888-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="c4888-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
