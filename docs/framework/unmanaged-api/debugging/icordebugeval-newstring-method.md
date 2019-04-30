---
title: ICorDebugEval::NewString-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db609bdee7975b6c067271f99529e2cf2240f720
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989026"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="b9b31-102">ICorDebugEval::NewString-Methode</span><span class="sxs-lookup"><span data-stu-id="b9b31-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="b9b31-103">Weist eine neue Zeichenfolgeninstanz mit dem angegebenen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="b9b31-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9b31-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9b31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9b31-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="b9b31-106">[in] Zeiger auf den Inhalt der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b9b31-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9b31-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9b31-107">Remarks</span></span>  
 <span data-ttu-id="b9b31-108">Die Zeichenfolge wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9b31-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b31-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9b31-109">Requirements</span></span>  
 <span data-ttu-id="b9b31-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9b31-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b31-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9b31-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9b31-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9b31-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9b31-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b31-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
