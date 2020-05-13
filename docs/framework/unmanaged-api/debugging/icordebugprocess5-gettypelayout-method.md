---
title: ICorDebugProcess5::GetTypeLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 861af4ba9c6f4d4bdb16abb9d4e1fd79debac59b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205574"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="2ccc1-102">ICorDebugProcess5::GetTypeLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="2ccc1-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="2ccc1-103">Ruft Informationen über das Layout eines Objekts im Arbeitsspeicher auf Grundlage des Typbezeichners ab.</span><span class="sxs-lookup"><span data-stu-id="2ccc1-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ccc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ccc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ccc1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ccc1-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="2ccc1-106">in Ein [COR_TYPEID](cor-typeid-structure.md) Token, das den Typ angibt, dessen Layout gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="2ccc1-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="2ccc1-107">vorgenommen Ein Zeiger auf eine [COR_TYPE_LAYOUT](cor-type-layout-structure.md) -Struktur, die Informationen über das Layout des-Objekts im Arbeitsspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="2ccc1-107">[out] A pointer to a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ccc1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ccc1-108">Remarks</span></span>  
 <span data-ttu-id="2ccc1-109">Die- `ICorDebugProcess5::GetTypeLayout` Methode stellt Informationen zu einem-Objekt auf der Grundlage des [COR_TYPEID](cor-typeid-structure.md)bereit, das von einer Reihe anderer [ICorDebugProcess5](icordebugprocess5-interface.md) -Methoden zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2ccc1-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="2ccc1-110">Die Informationen werden von einer [COR_TYPE_LAYOUT](cor-type-layout-structure.md) Struktur bereitgestellt, die von der-Methode aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="2ccc1-110">The information is provided by a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ccc1-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2ccc1-111">Requirements</span></span>  
 <span data-ttu-id="2ccc1-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ccc1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ccc1-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ccc1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ccc1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ccc1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ccc1-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ccc1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ccc1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ccc1-116">See also</span></span>

- [<span data-ttu-id="2ccc1-117">COR_TYPE_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="2ccc1-117">COR_TYPE_LAYOUT Structure</span></span>](cor-type-layout-structure.md)
- [<span data-ttu-id="2ccc1-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ccc1-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="2ccc1-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2ccc1-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
