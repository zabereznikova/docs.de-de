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
ms.openlocfilehash: f47263872b1baf1038a5fa9816c96e3e2569e705
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213217"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="88519-102">ICorDebugFunction2::GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="88519-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="88519-103">Ruft die Edit-und continue-Version dieser Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="88519-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88519-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88519-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88519-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="88519-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="88519-106">vorgenommen Ein Zeiger auf eine ganze Zahl, die die Versionsnummer der Funktion ist, die durch dieses ICorDebugFunction2-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="88519-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88519-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="88519-107">Remarks</span></span>  
 <span data-ttu-id="88519-108">Die Laufzeit verfolgt die Anzahl der Änderungen, die während einer Debugsitzung an den einzelnen Modulen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="88519-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="88519-109">Die Versionsnummer einer Funktion ist um eins größer als die Nummer der Bearbeitung, die die Funktion eingeführt hat.</span><span class="sxs-lookup"><span data-stu-id="88519-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="88519-110">Die ursprüngliche Version der Funktion ist Version 1.</span><span class="sxs-lookup"><span data-stu-id="88519-110">The function's original version is version 1.</span></span> <span data-ttu-id="88519-111">Die Zahl wird für ein Modul jedes Mal erhöht, wenn [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md) für dieses Modul aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="88519-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="88519-112">Wenn der Text einer Funktion im ersten und dritten-Vorgang ersetzt wurde `ICorDebugModule2::ApplyChanges` , `GetVersionNumber` gibt daher möglicherweise Version 1, 2 oder 4 für diese Funktion zurück, aber nicht Version 3.</span><span class="sxs-lookup"><span data-stu-id="88519-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="88519-113">(Diese Funktion hätte keine Version 3.)</span><span class="sxs-lookup"><span data-stu-id="88519-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="88519-114">Die Versionsnummer wird für jedes Modul separat nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="88519-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="88519-115">Wenn Sie also vier Bearbeitungen für Modul 1 und keine für Modul 2 durchführen, wird bei der nächsten Bearbeitung von Modul 1 die Versionsnummer 6 allen bearbeiteten Funktionen in Modul 1 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="88519-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="88519-116">Wenn das gleiche Bearbeitungsmodul 2 verwendet, erhalten die Funktionen in Modul 2 eine Versionsnummer von 2.</span><span class="sxs-lookup"><span data-stu-id="88519-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="88519-117">Die Versionsnummer, die von der- `GetVersionNumber` Methode abgerufen wird, ist möglicherweise niedriger als die von [ICorDebugFunction:: GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="88519-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="88519-118">Die [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) -Methode führt denselben Vorgang wie aus `ICorDebugFunction2::GetVersionNumber` .</span><span class="sxs-lookup"><span data-stu-id="88519-118">The [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88519-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="88519-119">Requirements</span></span>  
 <span data-ttu-id="88519-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88519-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88519-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88519-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88519-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88519-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88519-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88519-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
