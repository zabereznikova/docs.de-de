---
title: GetCORRequiredVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
ms.openlocfilehash: 9590d19f4e5f5890af53a108492bd1b6d130fb72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704499"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="9ea00-102">GetCORRequiredVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="9ea00-102">GetCORRequiredVersion Function</span></span>

<span data-ttu-id="9ea00-103">Ruft die erforderliche Common Language Runtime (CLR)-Versionsnummer ab.</span><span class="sxs-lookup"><span data-stu-id="9ea00-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="9ea00-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="9ea00-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea00-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ea00-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ea00-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ea00-106">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="9ea00-107">vorgenommen Ein Puffer, der eine Zeichenfolge enthält, die die Versionsnummer angibt.</span><span class="sxs-lookup"><span data-stu-id="9ea00-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9ea00-108">in Die Größe des Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="9ea00-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9ea00-109">vorgenommen Die Anzahl von Bytes, die im Puffer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9ea00-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea00-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9ea00-110">Requirements</span></span>  

 <span data-ttu-id="9ea00-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ea00-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea00-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9ea00-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ea00-113">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ea00-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ea00-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea00-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea00-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ea00-115">See also</span></span>

- [<span data-ttu-id="9ea00-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="9ea00-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
