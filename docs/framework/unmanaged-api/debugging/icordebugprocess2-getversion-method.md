---
title: ICorDebugProcess2::GetVersion-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f3be81431201a4bb6011ea9b8f973061d3d101
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361233"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="60cac-102">ICorDebugProcess2::GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="60cac-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="60cac-103">Ruft die Versionsnummer der die common Language Runtime (CLR), die in diesem Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="60cac-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="60cac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60cac-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="60cac-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60cac-105">Parameters</span></span>

`version`\
<span data-ttu-id="60cac-106">[out] Ein Zeiger auf eine COR_VERSION-Struktur, die die Versionsnummer der Laufzeit speichert.</span><span class="sxs-lookup"><span data-stu-id="60cac-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="60cac-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60cac-107">Remarks</span></span>

<span data-ttu-id="60cac-108">Die `GetVersion` Methode gibt einen Fehlercode zurück, wenn keine Laufzeit im Prozess geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="60cac-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="60cac-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60cac-109">Requirements</span></span>

<span data-ttu-id="60cac-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60cac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="60cac-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60cac-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="60cac-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60cac-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="60cac-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60cac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
