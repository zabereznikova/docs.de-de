---
title: ICorDebugProcess5::GetArrayLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: 8b7fab5fc5a02f8e43dc5f6fe8fc98087859ee3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671108"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="ebfce-102">ICorDebugProcess5::GetArrayLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="ebfce-102">ICorDebugProcess5::GetArrayLayout Method</span></span>

<span data-ttu-id="ebfce-103">Stellt Informationen über das Layout von Array Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="ebfce-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebfce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebfce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebfce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ebfce-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="ebfce-106">in Ein [COR_TYPEID](cor-typeid-structure.md) Token, das das Array angibt, dessen Layout gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="ebfce-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="ebfce-107">vorgenommen Ein Zeiger auf eine [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) Struktur, die Informationen über das Layout des Arrays im Arbeitsspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="ebfce-107">[out] A pointer to a [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebfce-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ebfce-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebfce-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ebfce-109">Requirements</span></span>  

 <span data-ttu-id="ebfce-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebfce-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebfce-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebfce-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebfce-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebfce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebfce-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebfce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebfce-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebfce-114">See also</span></span>

- [<span data-ttu-id="ebfce-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ebfce-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="ebfce-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ebfce-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
