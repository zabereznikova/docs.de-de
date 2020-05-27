---
title: RunDll32ShimW-Funktion
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
ms.openlocfilehash: 90304eb94e6f53d3132c97f5ababdc45f6053d7c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006570"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="9a660-102">RunDll32ShimW-Funktion</span><span class="sxs-lookup"><span data-stu-id="9a660-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="9a660-103">Führt den angegebenen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="9a660-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="9a660-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="9a660-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a660-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a660-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a660-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a660-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="9a660-107">in Ein Handle für ein Fenster, in dem die Befehlsausgabe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9a660-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="9a660-108">in Ein Handle für die Bibliothek, die den Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="9a660-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="9a660-109">in Eine Zeichenfolge, die den auszuführenden Befehl angibt.</span><span class="sxs-lookup"><span data-stu-id="9a660-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="9a660-110">in Eine ganze Zahl, die den Anzeigemodus für das Ausgabefenster angibt.</span><span class="sxs-lookup"><span data-stu-id="9a660-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a660-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9a660-111">Requirements</span></span>  
 <span data-ttu-id="9a660-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a660-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a660-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9a660-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a660-114">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9a660-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a660-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a660-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a660-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a660-116">See also</span></span>

- [<span data-ttu-id="9a660-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="9a660-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
