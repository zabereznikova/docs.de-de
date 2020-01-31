---
title: ICorDebugGuidToTypeEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 76cab0b8b5f16f24c62e31be2707c95c7e557034
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777646"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="57edf-102">ICorDebugGuidToTypeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="57edf-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="57edf-103">Ruft die angegebene Anzahl von [cordebugguidtoidetypemapping](cordebugguidtotypemapping-structure.md) -Instanzen ab, die GUIDs Typinformationen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="57edf-103">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57edf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57edf-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57edf-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="57edf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="57edf-106">in Die Anzahl der abzurufenden GUID-zu-Typ-Zuordnungsobjekte.</span><span class="sxs-lookup"><span data-stu-id="57edf-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="57edf-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein [cordebugguidtotypemapping](cordebugguidtotypemapping-structure.md) -Objekt verweist, das eine Windows-Runtime GUID dem entsprechenden ICorDebugType-Objekt zuordnet.</span><span class="sxs-lookup"><span data-stu-id="57edf-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="57edf-108">vorgenommen Ein Zeiger auf die Anzahl der [Cordebug](cordebugguidtotypemapping-structure.md) -Objekte, die tatsächlich in `values`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="57edf-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57edf-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57edf-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57edf-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57edf-110">Requirements</span></span>  
 <span data-ttu-id="57edf-111">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="57edf-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="57edf-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57edf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57edf-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57edf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57edf-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57edf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57edf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57edf-115">See also</span></span>

- [<span data-ttu-id="57edf-116">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57edf-116">ICorDebugGuidToTypeEnum Interface</span></span>](icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="57edf-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="57edf-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
