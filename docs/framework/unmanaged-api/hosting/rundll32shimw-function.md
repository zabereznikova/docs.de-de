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
ms.openlocfilehash: fa7df47ab55b8dc7ef3f55f5591b44614052bcee
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490137"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="73fe3-102">RunDll32ShimW-Funktion</span><span class="sxs-lookup"><span data-stu-id="73fe3-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="73fe3-103">Führt den angegebenen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="73fe3-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="73fe3-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="73fe3-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73fe3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="73fe3-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73fe3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="73fe3-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="73fe3-107">[in] Ein Handle für ein Fenster, in der Ausgabe des Befehls angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="73fe3-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="73fe3-108">[in] Ein Handle für die Bibliothek, die den Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="73fe3-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="73fe3-109">[in] Eine Zeichenfolge, die angibt, den Befehl ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="73fe3-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="73fe3-110">[in] Eine ganze Zahl, die den Anzeigemodus für das Fenster "Ausgabe" angibt.</span><span class="sxs-lookup"><span data-stu-id="73fe3-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73fe3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73fe3-111">Requirements</span></span>  
 <span data-ttu-id="73fe3-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73fe3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73fe3-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="73fe3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73fe3-114">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73fe3-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73fe3-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73fe3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73fe3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73fe3-116">See also</span></span>

- [<span data-ttu-id="73fe3-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="73fe3-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
