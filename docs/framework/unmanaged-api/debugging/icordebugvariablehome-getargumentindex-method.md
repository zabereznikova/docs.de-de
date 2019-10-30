---
title: 'Icordebugvariablehome:: getargumentindex-Methode'
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
ms.openlocfilehash: 86b2815c6f95c674c49bba7455e8497192bd8bac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125154"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="d74fc-102">Icordebugvariablehome:: getargumentindex-Methode</span><span class="sxs-lookup"><span data-stu-id="d74fc-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="d74fc-103">Ruft den Index eines Funktionsarguments ab.</span><span class="sxs-lookup"><span data-stu-id="d74fc-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="d74fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d74fc-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="d74fc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d74fc-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="d74fc-106">vorgenommen Ein Zeiger auf den Argument index.</span><span class="sxs-lookup"><span data-stu-id="d74fc-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="d74fc-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d74fc-107">Return Value</span></span>

<span data-ttu-id="d74fc-108">Die-Methode gibt die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d74fc-108">The method returns the following values.</span></span>

|<span data-ttu-id="d74fc-109">Wert</span><span class="sxs-lookup"><span data-stu-id="d74fc-109">Value</span></span>|<span data-ttu-id="d74fc-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d74fc-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="d74fc-111">Der Methodenaufrufe hat einen gültigen Argument Index zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d74fc-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="d74fc-112">Die aktuelle [icorentbugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Instanz stellt eine lokale Variable dar.</span><span class="sxs-lookup"><span data-stu-id="d74fc-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d74fc-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d74fc-113">Remarks</span></span>

<span data-ttu-id="d74fc-114">Der Argument Index kann zum Abrufen von Metadaten für dieses Argument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d74fc-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="d74fc-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d74fc-115">Requirements</span></span>

<span data-ttu-id="d74fc-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d74fc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d74fc-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d74fc-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="d74fc-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d74fc-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d74fc-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d74fc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d74fc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d74fc-120">See also</span></span>

- [<span data-ttu-id="d74fc-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d74fc-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
