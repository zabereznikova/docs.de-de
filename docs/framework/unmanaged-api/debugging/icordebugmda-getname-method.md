---
title: ICorDebugMDA::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 6a6769265a2e140f1fa001bb8240bc5d4bd76018
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213672"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="5974c-102">ICorDebugMDA::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="5974c-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="5974c-103">Ruft eine Zeichenfolge ab, die den Namen des von [ICorDebugMDA](icordebugmda-interface.md)dargestellten Assistenten für verwaltetes Debuggen (MDA) enthält.</span><span class="sxs-lookup"><span data-stu-id="5974c-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5974c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5974c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5974c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5974c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5974c-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="5974c-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5974c-107">vorgenommen Ein Zeiger auf die Länge des Namens.</span><span class="sxs-lookup"><span data-stu-id="5974c-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="5974c-108">vorgenommen Ein Array, in dem der Name gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5974c-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5974c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5974c-109">Remarks</span></span>  
 <span data-ttu-id="5974c-110">MDA-Namen sind eindeutige Werte.</span><span class="sxs-lookup"><span data-stu-id="5974c-110">MDA names are unique values.</span></span> <span data-ttu-id="5974c-111">Die `GetName` -Methode ist eine bequeme Leistungs Alternative, um den XML-Stream zu erhalten und den Namen basierend auf dem Schema aus dem Stream zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="5974c-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5974c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5974c-112">Requirements</span></span>  
 <span data-ttu-id="5974c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5974c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5974c-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5974c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5974c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5974c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5974c-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5974c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5974c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5974c-117">See also</span></span>

- [<span data-ttu-id="5974c-118">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5974c-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="5974c-119">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="5974c-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
