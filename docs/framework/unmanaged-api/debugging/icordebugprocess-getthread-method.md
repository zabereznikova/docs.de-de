---
title: ICorDebugProcess::GetThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
ms.openlocfilehash: 6bf73a4be40f1fbd8e9d37477907001604e8e4a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128819"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="44be1-102">ICorDebugProcess::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="44be1-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="44be1-103">Ruft den Thread des Prozesses ab, der über die angegebene Betriebssystem Thread-ID verfügt.</span><span class="sxs-lookup"><span data-stu-id="44be1-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44be1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44be1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44be1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44be1-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="44be1-106">in Die ID des Betriebssystem Threads des abzurufenden Threads.</span><span class="sxs-lookup"><span data-stu-id="44be1-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="44be1-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThread-Objekts, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="44be1-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44be1-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44be1-108">Requirements</span></span>  
 <span data-ttu-id="44be1-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44be1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44be1-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44be1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44be1-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44be1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44be1-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44be1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
