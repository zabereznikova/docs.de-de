---
title: ICorDebugProcess::GetID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ebdf0dd2457cd10e31ff71c32b1c09d0e014431
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765995"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="bb98b-102">ICorDebugProcess::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="bb98b-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="bb98b-103">Ruft das Betriebssystem (OS)-ID des Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="bb98b-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb98b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb98b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb98b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb98b-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="bb98b-106">[out] Die eindeutige ID des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="bb98b-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb98b-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb98b-107">Requirements</span></span>  
 <span data-ttu-id="bb98b-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb98b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb98b-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb98b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb98b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb98b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb98b-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb98b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
