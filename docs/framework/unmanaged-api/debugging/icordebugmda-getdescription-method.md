---
title: ICorDebugMDA::GetDescription-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
ms.openlocfilehash: bfe77982b88b2fc96dc2846b9db04df28bfc0c38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131446"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="002f5-102">ICorDebugMDA::GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="002f5-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="002f5-103">Ruft eine Zeichenfolge ab, die die Beschreibung des von [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)dargestellten Assistenten für verwaltetes Debuggen (MDA) enthält.</span><span class="sxs-lookup"><span data-stu-id="002f5-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="002f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="002f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="002f5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="002f5-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="002f5-106">in Die Größe des Zeichen folgen Puffers, in dem die Beschreibung gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="002f5-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="002f5-107">vorgenommen Ein Zeiger auf die Anzahl von Bytes, die im Zeichen folgen Puffer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="002f5-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="002f5-108">vorgenommen Ein Zeichen folgen Puffer, der die Beschreibung des MDA enthält.</span><span class="sxs-lookup"><span data-stu-id="002f5-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="002f5-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="002f5-109">Remarks</span></span>  
 <span data-ttu-id="002f5-110">Die Zeichenfolge kann eine Länge von NULL aufweisen.</span><span class="sxs-lookup"><span data-stu-id="002f5-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="002f5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="002f5-111">Requirements</span></span>  
 <span data-ttu-id="002f5-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="002f5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="002f5-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="002f5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="002f5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="002f5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="002f5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="002f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002f5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="002f5-116">See also</span></span>

- [<span data-ttu-id="002f5-117">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="002f5-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="002f5-118">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="002f5-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
