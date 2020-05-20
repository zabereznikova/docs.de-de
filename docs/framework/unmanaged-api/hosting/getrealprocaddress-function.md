---
title: GetRealProcAddress-Funktion
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: 6bbf8366054c58543444a4b710a687198f365e6e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617190"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="09f31-102">GetRealProcAddress-Funktion</span><span class="sxs-lookup"><span data-stu-id="09f31-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="09f31-103">Ruft die Adresse der angegebenen Funktion ab, die von der neuesten installierten Version des Common Language Runtime (CLR) exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="09f31-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="09f31-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="09f31-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09f31-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="09f31-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09f31-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="09f31-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="09f31-107">in Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="09f31-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="09f31-108">vorgenommen Die Position, an der ein Zeiger auf die Adresse der Funktion empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="09f31-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09f31-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="09f31-109">Return Value</span></span>  
 <span data-ttu-id="09f31-110">Diese Methode gibt zusätzlich zu den folgenden Werten, die in "CorError. h" definiert sind, Standard-Component Object Model (com)-Fehlercodes zurück, wie in WinError. h definiert.</span><span class="sxs-lookup"><span data-stu-id="09f31-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="09f31-111">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="09f31-111">Return code</span></span>|<span data-ttu-id="09f31-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="09f31-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="09f31-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="09f31-113">S_OK</span></span>|<span data-ttu-id="09f31-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="09f31-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="09f31-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="09f31-115">E_POINTER</span></span>|<span data-ttu-id="09f31-116">`ppv` ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="09f31-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="09f31-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="09f31-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="09f31-118">Die Funktion wird nicht aus der Laufzeit exportiert.</span><span class="sxs-lookup"><span data-stu-id="09f31-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09f31-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09f31-119">Requirements</span></span>  
 <span data-ttu-id="09f31-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09f31-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09f31-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="09f31-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09f31-122">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="09f31-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09f31-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09f31-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f31-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09f31-124">See also</span></span>

- [<span data-ttu-id="09f31-125">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="09f31-125">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
