---
title: ICorPublishAppDomain::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 796f8ea42cc5cbe13729f7b92e15bc214d62734d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423857"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="ece86-102">ICorPublishAppDomain::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="ece86-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="ece86-103">Ruft den Namen der Anwendungsdomäne, die von diesem dargestellt wird [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ece86-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ece86-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ece86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ece86-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ece86-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="ece86-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ece86-107">[out] Ein Zeiger auf die Anzahl der Breitzeichen, einschließlich der Null-Zeichen im zurückgegebenen den `szName` Array.</span><span class="sxs-lookup"><span data-stu-id="ece86-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="ece86-108">[out] Ein Array, in dem Sie den Namen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ece86-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ece86-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ece86-109">Remarks</span></span>  
 <span data-ttu-id="ece86-110">Wenn `szName` ungleich Null ist, wird die `GetName` -Methode kopiert bis zu `cchName` Zeichen (einschließlich der null-Terminator) in `szName`.</span><span class="sxs-lookup"><span data-stu-id="ece86-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="ece86-111">Wenn eine Wert ungleich Null, in zurückgegeben wird `pcchName`, die tatsächliche Anzahl der Zeichen im Namen (einschließlich der null-Abschlusszeichen) befindet sich in der `szName` Array.</span><span class="sxs-lookup"><span data-stu-id="ece86-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="ece86-112">Die `GetName` Methode gibt ein HRESULT S_OK zurück, unabhängig davon, wie viele Zeichen kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ece86-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ece86-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ece86-113">Requirements</span></span>  
 <span data-ttu-id="ece86-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ece86-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ece86-115">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ece86-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ece86-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ece86-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ece86-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ece86-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece86-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ece86-118">See Also</span></span>  
 [<span data-ttu-id="ece86-119">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ece86-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
