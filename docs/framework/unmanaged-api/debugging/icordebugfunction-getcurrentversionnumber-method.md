---
title: ICorDebugFunction::GetCurrentVersionNumber-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: b47580022b98ea02584a94b3f74b3fd1c276f297
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212905"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="62e1b-102">ICorDebugFunction::GetCurrentVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="62e1b-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="62e1b-103">Ruft die Versionsnummer der letzten Bearbeitung der Funktion ab, die von diesem ICorDebugFunction-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="62e1b-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62e1b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62e1b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62e1b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62e1b-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="62e1b-106">vorgenommen Ein Zeiger auf einen ganzzahligen Wert, der die Versionsnummer der letzten Bearbeitung ist, die an dieser Funktion vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="62e1b-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62e1b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62e1b-107">Remarks</span></span>  
 <span data-ttu-id="62e1b-108">Die Versionsnummer der aktuellen Bearbeitung, die an dieser Funktion vorgenommen wurde, ist möglicherweise größer als die Versionsnummer der Funktion selbst.</span><span class="sxs-lookup"><span data-stu-id="62e1b-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="62e1b-109">Verwenden Sie entweder die [ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) -Methode oder die [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) -Methode, um die Versionsnummer der Funktion abzurufen.</span><span class="sxs-lookup"><span data-stu-id="62e1b-109">Use either the [ICorDebugFunction2::GetVersionNumber](icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62e1b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="62e1b-110">Requirements</span></span>  
 <span data-ttu-id="62e1b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62e1b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62e1b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62e1b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62e1b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62e1b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62e1b-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62e1b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
