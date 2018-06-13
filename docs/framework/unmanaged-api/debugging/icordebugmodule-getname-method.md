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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bebee019595143d25e950719ad62d9e10b76a3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418905"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="a5491-102">ICorDebugModule::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="a5491-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="a5491-103">Ruft den Dateinamen des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="a5491-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5491-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5491-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5491-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5491-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="a5491-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a5491-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a5491-107">[in] Ein Zeiger auf die Länge des zurückgegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="a5491-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="a5491-108">[out] Ein Array, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="a5491-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5491-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5491-109">Remarks</span></span>  
 <span data-ttu-id="a5491-110">Die `GetName` Methode gibt ein S_OK HRESULT aus, wenn der Dateiname für das Modul mit dem Namen auf dem Datenträger übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a5491-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="a5491-111">`GetName` Gibt HRESULT "S_FALSE" zurück, wenn der Name, erstellt wurde, z. B. für ein dynamisches oder in-Memory-Modul ist.</span><span class="sxs-lookup"><span data-stu-id="a5491-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5491-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5491-112">Requirements</span></span>  
 <span data-ttu-id="a5491-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5491-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5491-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5491-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5491-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5491-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5491-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5491-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5491-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5491-117">See Also</span></span>  
    
 
