---
title: 'Icordebugvariablehome:: gedeffset-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: 75a165e2fd517f36d779a934a5bdd9c41956411a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396764"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="56125-102">Icordebugvariablehome:: gedeffset-Methode</span><span class="sxs-lookup"><span data-stu-id="56125-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="56125-103">Ruft den Offset aus dem Basisregister für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="56125-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56125-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="56125-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56125-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="56125-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="56125-106">vorgenommen Der Offset aus dem Basisregister.</span><span class="sxs-lookup"><span data-stu-id="56125-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56125-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="56125-107">Return Value</span></span>  
 <span data-ttu-id="56125-108">Die-Methode gibt die folgenden Werte zurück:</span><span class="sxs-lookup"><span data-stu-id="56125-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="56125-109">Wert</span><span class="sxs-lookup"><span data-stu-id="56125-109">Value</span></span>|<span data-ttu-id="56125-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56125-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="56125-111">Die Variable befindet sich in einer Register-relativen Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="56125-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="56125-112">Die-Variable befindet sich nicht in einem Register-relativen Speicher Speicherort.</span><span class="sxs-lookup"><span data-stu-id="56125-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56125-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="56125-113">Requirements</span></span>  
 <span data-ttu-id="56125-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56125-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56125-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56125-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56125-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56125-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56125-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56125-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56125-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56125-118">See also</span></span>

- [<span data-ttu-id="56125-119">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="56125-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
