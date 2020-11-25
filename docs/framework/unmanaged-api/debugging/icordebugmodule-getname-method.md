---
title: ICorDebugModule::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
ms.openlocfilehash: c2aecadf8688e763a69bd40ca877e44bc0ce5c29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710033"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="51c65-102">ICorDebugModule::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="51c65-102">ICorDebugModule::GetName Method</span></span>

<span data-ttu-id="51c65-103">Ruft den Dateinamen des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="51c65-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51c65-104">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51c65-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="51c65-105">Parameters</span></span>  

 `cchname`  
 <span data-ttu-id="51c65-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="51c65-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="51c65-107">in Ein Zeiger auf die Länge des zurückgegebenen Namens.</span><span class="sxs-lookup"><span data-stu-id="51c65-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="51c65-108">vorgenommen Ein Array, in dem der zurückgegebene Name gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="51c65-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51c65-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51c65-109">Remarks</span></span>  

 <span data-ttu-id="51c65-110">Die `GetName` -Methode gibt eine S_OK HRESULT zurück, wenn der Dateiname des Moduls mit dem Namen auf dem Datenträger übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="51c65-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="51c65-111">`GetName` gibt eine S_FALSE HRESULT zurück, wenn der Name erfunden ist, z. b. für ein dynamisches Modul oder ein in-Memory-Modul.</span><span class="sxs-lookup"><span data-stu-id="51c65-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51c65-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="51c65-112">Requirements</span></span>  

 <span data-ttu-id="51c65-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51c65-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51c65-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51c65-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51c65-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51c65-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51c65-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51c65-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c65-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51c65-117">See also</span></span>
