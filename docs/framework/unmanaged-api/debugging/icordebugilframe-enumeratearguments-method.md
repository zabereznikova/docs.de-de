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
ms.openlocfilehash: 9b0bc59b67b5d4b2184733f22616433bf33be616
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703225"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="a412c-102">ICorDebugILFrame::EnumerateArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="a412c-102">ICorDebugILFrame::EnumerateArguments Method</span></span>

<span data-ttu-id="a412c-103">Ruft einen Enumerator für die Argumente in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="a412c-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a412c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a412c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a412c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a412c-105">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="a412c-106">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalueenum-Objekts, das der Enumerator für die Argumente in diesem Frame ist.</span><span class="sxs-lookup"><span data-stu-id="a412c-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a412c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a412c-107">Remarks</span></span>  

 <span data-ttu-id="a412c-108">`EnumerateArguments` Ruft einen Enumerator ab, der die Argumente auflisten kann, die in dem von diesem ICorDebugILFrame-Objekt dargestellten callframe verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a412c-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="a412c-109">Die Liste enthält Argumente, die [vararg](/cpp/windows/vararg) sind (d. h. eine Variable Anzahl von Argumenten), sowie Argumente, die nicht sind `vararg` .</span><span class="sxs-lookup"><span data-stu-id="a412c-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a412c-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a412c-110">Requirements</span></span>  

 <span data-ttu-id="a412c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a412c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a412c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a412c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a412c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a412c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a412c-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a412c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
