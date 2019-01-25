---
title: ICorDebugObjectValue2::GetVirtualMethodAndType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af07df53c094654ab86f5e6531fd78124aded988
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630891"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="becd2-102">ICorDebugObjectValue2::GetVirtualMethodAndType-Methode</span><span class="sxs-lookup"><span data-stu-id="becd2-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="becd2-103">Diese Methode ist noch nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="becd2-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="becd2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="becd2-104">Syntax</span></span>  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="becd2-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="becd2-105">Remarks</span></span>  
 <span data-ttu-id="becd2-106">Ruft die Schnittstellenzeiger auf die "ICorDebugFunction" und "ICorDebugType"-Instanzen, die am stärksten abgeleiteten Methode und Typ für den angegebenen Memberverweis darstellen.</span><span class="sxs-lookup"><span data-stu-id="becd2-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="becd2-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="becd2-107">See also</span></span>


