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
ms.openlocfilehash: 12d4e63480f03bfad613f30362ddaeaf12b57a88
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791051"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="88a56-102">Icordebugvariablehome:: getargumentindex-Methode</span><span class="sxs-lookup"><span data-stu-id="88a56-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="88a56-103">Ruft den Index eines Funktionsarguments ab.</span><span class="sxs-lookup"><span data-stu-id="88a56-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="88a56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88a56-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="88a56-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="88a56-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="88a56-106">vorgenommen Ein Zeiger auf den Argument index.</span><span class="sxs-lookup"><span data-stu-id="88a56-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="88a56-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="88a56-107">Return Value</span></span>

<span data-ttu-id="88a56-108">Die-Methode gibt die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="88a56-108">The method returns the following values.</span></span>

|<span data-ttu-id="88a56-109">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="88a56-109">Value</span></span>|<span data-ttu-id="88a56-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88a56-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="88a56-111">Der Methodenaufrufe hat einen gültigen Argument Index zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="88a56-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="88a56-112">Die aktuelle [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz stellt eine lokale Variable dar.</span><span class="sxs-lookup"><span data-stu-id="88a56-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="88a56-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="88a56-113">Remarks</span></span>

<span data-ttu-id="88a56-114">Der Argument Index kann zum Abrufen von Metadaten für dieses Argument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88a56-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="88a56-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88a56-115">Requirements</span></span>

<span data-ttu-id="88a56-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88a56-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="88a56-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88a56-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="88a56-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88a56-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="88a56-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88a56-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="88a56-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88a56-120">See also</span></span>

- [<span data-ttu-id="88a56-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="88a56-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
