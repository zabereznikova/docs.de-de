---
title: ICorDebugFunction2::GetVersionNumber-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89cf2a12b0a693bbed3e8a3c1134d0f2b2a72a30
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754448"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="446ae-102">ICorDebugFunction2::GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="446ae-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="446ae-103">Ruft die bearbeiten und Fortfahren-Version dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="446ae-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="446ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="446ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="446ae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="446ae-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="446ae-106">[out] Ein Zeiger auf eine ganze Zahl, die Versionsnummer der Funktion, die von diesem ICorDebugFunction2-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="446ae-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="446ae-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="446ae-107">Remarks</span></span>  
 <span data-ttu-id="446ae-108">Der Common Language Runtime behält den Überblick über die Anzahl der Änderungen, die jedes Modul während einer Debugsitzung stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="446ae-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="446ae-109">Die Versionsnummer einer Funktion ist eine mehr als die Anzahl der Bearbeitung, die die Funktion eingeführt.</span><span class="sxs-lookup"><span data-stu-id="446ae-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="446ae-110">Ursprüngliche Version der Funktion ist die Version 1.</span><span class="sxs-lookup"><span data-stu-id="446ae-110">The function's original version is version 1.</span></span> <span data-ttu-id="446ae-111">Jedes Mal die Anzahl für ein Modul erhöht [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) für das Modul aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="446ae-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="446ae-112">Daher, wenn in der ersten und dritten Aufruf einer Funktion Text ersetzt wurde `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` möglicherweise Version 1, 2 oder 4 für diese Funktion, jedoch nicht Version 3 zurück.</span><span class="sxs-lookup"><span data-stu-id="446ae-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="446ae-113">(Diese Funktion müssten keine Version 3.)</span><span class="sxs-lookup"><span data-stu-id="446ae-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="446ae-114">Die Versionsnummer wird für jedes Modul separat nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="446ae-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="446ae-115">Also wenn Sie vier Änderungen auf die Modul1 und keine in Module2 ausführen, wird die nächste Bearbeitung Modul 1 eine Versionsnummer von 6 alle bearbeiteten Funktionen im Modul1 zuweisen.</span><span class="sxs-lookup"><span data-stu-id="446ae-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="446ae-116">Wenn es sich bei dem Bearbeitungsvorgang Module2, erhalten die Funktionen im Module2 eine Versionsnummer von 2.</span><span class="sxs-lookup"><span data-stu-id="446ae-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="446ae-117">Die Versionsnummer abgerufen, indem die `GetVersionNumber` Methode ist möglicherweise niedriger als die von [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="446ae-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="446ae-118">Die [ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) Methode führt den gleichen Vorgang wie `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="446ae-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="446ae-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="446ae-119">Requirements</span></span>  
 <span data-ttu-id="446ae-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="446ae-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="446ae-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="446ae-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="446ae-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="446ae-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="446ae-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="446ae-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
