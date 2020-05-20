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
ms.openlocfilehash: e8945d40a3761ec51a73a8ae90ddc1d84ccab651
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616865"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="8ac92-102">CallFunctionShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="8ac92-102">CallFunctionShim Function</span></span>
<span data-ttu-id="8ac92-103">Ruft eine Funktion mit dem angegebenen Namen und den angegebenen Parametern in der angegebenen Bibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="8ac92-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="8ac92-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="8ac92-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ac92-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ac92-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ac92-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ac92-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="8ac92-107">in Der Name der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="8ac92-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="8ac92-108">in Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="8ac92-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="8ac92-109">in Das erste Argument, das an die Funktion übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ac92-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="8ac92-110">in Das zweite Argument, das an die Funktion übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ac92-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="8ac92-111">in Die Version der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="8ac92-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8ac92-112">[in] Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="8ac92-112">[in] Reserved for future use.</span></span> <span data-ttu-id="8ac92-113">NULL in diesem Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="8ac92-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ac92-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ac92-114">Requirements</span></span>  
 <span data-ttu-id="8ac92-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ac92-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ac92-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8ac92-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ac92-117">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8ac92-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ac92-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ac92-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac92-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ac92-119">See also</span></span>

- [<span data-ttu-id="8ac92-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="8ac92-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
