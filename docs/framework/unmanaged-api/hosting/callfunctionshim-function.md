---
title: CallFunctionShim-Funktion
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dfe2c98fd5898a0ad5a1d4fd9e89c7f20741bb0
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490696"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="a69fc-102">CallFunctionShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="a69fc-102">CallFunctionShim Function</span></span>
<span data-ttu-id="a69fc-103">Ruft eine Funktion mit dem angegebenen Namen und den angegebenen Parametern in der angegebenen Bibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="a69fc-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="a69fc-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="a69fc-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a69fc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a69fc-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a69fc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a69fc-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="a69fc-107">[in] Der Name der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="a69fc-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="a69fc-108">[in] Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="a69fc-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="a69fc-109">[in] Das erste Argument an die Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="a69fc-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="a69fc-110">[in] Das zweite Argument an die Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="a69fc-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="a69fc-111">[in] Die Version der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="a69fc-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a69fc-112">[in] Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="a69fc-112">[in] Reserved for future use.</span></span> <span data-ttu-id="a69fc-113">Übergeben Sie 0 (null), in diesem Parameter.</span><span class="sxs-lookup"><span data-stu-id="a69fc-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a69fc-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a69fc-114">Requirements</span></span>  
 <span data-ttu-id="a69fc-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a69fc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a69fc-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a69fc-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a69fc-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a69fc-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a69fc-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a69fc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69fc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a69fc-119">See also</span></span>

- [<span data-ttu-id="a69fc-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="a69fc-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
