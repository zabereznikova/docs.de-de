---
title: ICorDebugILFrame::EnumerateArguments-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49d7fb1de0b2ea63c1a766023b23acc42e027af8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475657"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="075b9-102">ICorDebugILFrame::EnumerateArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="075b9-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="075b9-103">Ruft einen Enumerator für die Argumente in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="075b9-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="075b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="075b9-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="075b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="075b9-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="075b9-106">[out] Ein Zeiger auf die Adresse des ICorDebugValueEnum-Objekts, das den Enumerator für die Argumente in diesem Frame ist.</span><span class="sxs-lookup"><span data-stu-id="075b9-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="075b9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="075b9-107">Remarks</span></span>  
 <span data-ttu-id="075b9-108">`EnumerateArguments` Ruft einen Enumerator aus, der den Argumenten, die in den Aufrufframe auflisten kann, die von diesem ICorDebugILFrame-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="075b9-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="075b9-109">Die Liste enthält Argumente, die sind [Vararg](/cpp/windows/vararg) (d. h. eine Variable Anzahl von Argumenten) sowie Argumente, die nicht `vararg`.</span><span class="sxs-lookup"><span data-stu-id="075b9-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="075b9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="075b9-110">Requirements</span></span>  
 <span data-ttu-id="075b9-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="075b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="075b9-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="075b9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="075b9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="075b9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="075b9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="075b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
