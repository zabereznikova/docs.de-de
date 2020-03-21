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
ms.openlocfilehash: 762c637696fdf79ccab6702918b5bf962ea55903
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178409"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="faf82-102">ICorPublishAppDomain::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="faf82-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="faf82-103">Ruft den Namen der Anwendungsdomäne ab, die durch diese [ICorPublishAppDomain](icorpublishappdomain-interface.md)dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="faf82-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="faf82-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faf82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="faf82-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="faf82-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="faf82-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="faf82-107">[out] Ein Zeiger auf die Anzahl der breiten Zeichen, einschließlich `szName` des Nullzeichens, die im Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="faf82-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="faf82-108">[out] Ein Array, in dem der Name gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="faf82-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faf82-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="faf82-109">Remarks</span></span>  
 <span data-ttu-id="faf82-110">Wenn `szName` es sich um `GetName` ungleich `cchName` NULL handelt, kopiert die `szName`Methode Zeichen (einschließlich des Nullabschlusses) in .</span><span class="sxs-lookup"><span data-stu-id="faf82-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="faf82-111">Wenn ein Nicht-NULL-Zeichen in `pcchName`zurückgegeben wird, wird die tatsächliche Anzahl der `szName` Zeichen im Namen (einschließlich des Nullabschlusses) im Array gespeichert.</span><span class="sxs-lookup"><span data-stu-id="faf82-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="faf82-112">Die `GetName` Methode gibt eine S_OK HRESULT zurück, unabhängig davon, wie viele Zeichen kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="faf82-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faf82-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="faf82-113">Requirements</span></span>  
 <span data-ttu-id="faf82-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faf82-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf82-115">**Kopfzeile:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="faf82-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="faf82-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faf82-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faf82-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faf82-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf82-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="faf82-118">See also</span></span>

- [<span data-ttu-id="faf82-119">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="faf82-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
