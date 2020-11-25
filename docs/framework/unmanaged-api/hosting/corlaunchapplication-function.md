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
ms.openlocfilehash: ca427439f03d92b20e7714b9724d90b240e9cecb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704070"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="1a335-102">CorLaunchApplication-Funktion</span><span class="sxs-lookup"><span data-stu-id="1a335-102">CorLaunchApplication Function</span></span>

<span data-ttu-id="1a335-103">Startet die Anwendung im angegebenen Netzwerkpfad, wobei die angegebenen Manifeste und sonstigen Anwendungsdaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a335-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="1a335-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="1a335-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a335-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a335-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="1a335-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1a335-106">Parameters</span></span>  

 `dwClickOnceHost`  
 <span data-ttu-id="1a335-107">in Ein Wert der [HOST_TYPE](host-type-enumeration.md) -Enumeration, die den Typ des Hosts angibt, der die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="1a335-107">[in] A value of the [HOST_TYPE](host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="1a335-108">in Der vollständige Name der Anwendung, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a335-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="1a335-109">in Die Anzahl der manifestressfade für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1a335-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="1a335-110">in Ein Array von Zeichen folgen, von denen jede einen Pfad zu einem Manifest für die Anwendung angibt, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a335-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="1a335-111">in Die Anzahl der Aktivierungsdaten Elemente für die Anwendung, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a335-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="1a335-112">in Ein Array von Zeichen folgen, von denen jedes ein Aktivierungsdaten Element für die Anwendung ist, die gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a335-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="1a335-113">vorgenommen Ein Zeiger auf Informationen über den Prozess, in dem die Anwendung geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a335-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a335-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1a335-114">Requirements</span></span>  

 <span data-ttu-id="1a335-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a335-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a335-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1a335-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a335-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a335-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a335-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a335-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a335-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a335-119">See also</span></span>

- [<span data-ttu-id="1a335-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="1a335-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
