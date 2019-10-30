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
ms.openlocfilehash: 5f618f6779f6931785bba18f70fb1ac9baf46753
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137189"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="6390c-102">ICorDebugProcess2::GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="6390c-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="6390c-103">Ruft die Versionsnummer der Common Language Runtime (CLR) ab, die in diesem Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6390c-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="6390c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6390c-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="6390c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6390c-105">Parameters</span></span>

`version`\
<span data-ttu-id="6390c-106">vorgenommen Ein Zeiger auf eine COR_VERSION-Struktur, die die Versionsnummer der Laufzeit speichert.</span><span class="sxs-lookup"><span data-stu-id="6390c-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="6390c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6390c-107">Remarks</span></span>

<span data-ttu-id="6390c-108">Die `GetVersion`-Methode gibt einen Fehlercode zurück, wenn keine Laufzeit in den Prozess geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="6390c-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="6390c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6390c-109">Requirements</span></span>

<span data-ttu-id="6390c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6390c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6390c-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6390c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="6390c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6390c-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6390c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6390c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
