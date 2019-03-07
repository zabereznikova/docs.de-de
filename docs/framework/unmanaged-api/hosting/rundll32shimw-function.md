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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 336fba6defc00eb87fcfa7e6b1aaafa0fcb15691
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494206"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="61080-102">RunDll32ShimW-Funktion</span><span class="sxs-lookup"><span data-stu-id="61080-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="61080-103">Führt den angegebenen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="61080-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="61080-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="61080-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61080-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="61080-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61080-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="61080-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="61080-107">[in] Ein Handle für ein Fenster, in der Ausgabe des Befehls angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="61080-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="61080-108">[in] Ein Handle für die Bibliothek, die den Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="61080-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="61080-109">[in] Eine Zeichenfolge, die angibt, den Befehl ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="61080-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="61080-110">[in] Eine ganze Zahl, die den Anzeigemodus für das Fenster "Ausgabe" angibt.</span><span class="sxs-lookup"><span data-stu-id="61080-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61080-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61080-111">Requirements</span></span>  
 <span data-ttu-id="61080-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61080-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61080-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61080-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61080-114">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61080-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61080-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61080-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61080-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61080-116">See also</span></span>
- [<span data-ttu-id="61080-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="61080-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
