---
title: ICorDebugVariableHome::GetArgumentIndex-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2457dff3063e47f1fb9d040caac1bc08441e1739
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366828"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="e3ded-102">ICorDebugVariableHome::GetArgumentIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="e3ded-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="e3ded-103">Ruft den Index ein Funktionsargument ab.</span><span class="sxs-lookup"><span data-stu-id="e3ded-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3ded-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3ded-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="e3ded-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3ded-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="e3ded-106">[out] Ein Zeiger auf den Argumentindex.</span><span class="sxs-lookup"><span data-stu-id="e3ded-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="e3ded-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e3ded-107">Return Value</span></span>

<span data-ttu-id="e3ded-108">Die Methode gibt die folgenden Werte an.</span><span class="sxs-lookup"><span data-stu-id="e3ded-108">The method returns the following values.</span></span>

|<span data-ttu-id="e3ded-109">Wert</span><span class="sxs-lookup"><span data-stu-id="e3ded-109">Value</span></span>|<span data-ttu-id="e3ded-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3ded-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="e3ded-111">Aufruf der Methode wurde einen gültiges Argument-Index.</span><span class="sxs-lookup"><span data-stu-id="e3ded-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="e3ded-112">Die aktuelle [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanz stellt eine lokale Variable dar.</span><span class="sxs-lookup"><span data-stu-id="e3ded-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e3ded-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3ded-113">Remarks</span></span>

<span data-ttu-id="e3ded-114">Der Argumentindex kann zum Abrufen von Metadaten für dieses Argument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3ded-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3ded-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3ded-115">Requirements</span></span>

<span data-ttu-id="e3ded-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3ded-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e3ded-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3ded-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="e3ded-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3ded-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e3ded-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3ded-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e3ded-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3ded-120">See also</span></span>

- [<span data-ttu-id="e3ded-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3ded-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
