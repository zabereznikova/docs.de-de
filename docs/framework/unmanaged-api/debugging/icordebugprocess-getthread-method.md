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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 008f945b5301894261ce1529cbd915dd614b919d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418954"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="1b130-102">ICorDebugProcess::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="1b130-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="1b130-103">Ruft dieser Prozess Thread, der die angegebene Betriebssystem (BS)-Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="1b130-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b130-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b130-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b130-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b130-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="1b130-106">[in] Die Betriebssystem-thread-ID des Threads abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1b130-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="1b130-107">[out] Ein Zeiger auf die Adresse eines ICorDebugThread-Objekts, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="1b130-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b130-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b130-108">Requirements</span></span>  
 <span data-ttu-id="1b130-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b130-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b130-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b130-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b130-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b130-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b130-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b130-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
