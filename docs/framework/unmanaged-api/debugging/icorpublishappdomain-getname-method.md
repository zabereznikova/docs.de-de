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
ms.openlocfilehash: d6b05333b9e02c4202c0fd9bdee9b5c055aa4da3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694359"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="d33a8-102">ICorPublishAppDomain::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="d33a8-102">ICorPublishAppDomain::GetName Method</span></span>

<span data-ttu-id="d33a8-103">Ruft den Namen der Anwendungsdomäne ab, die von dieser [ICorPublishAppDomain](icorpublishappdomain-interface.md)dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d33a8-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d33a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d33a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d33a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d33a8-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="d33a8-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="d33a8-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d33a8-107">vorgenommen Ein Zeiger auf die Anzahl der breit Zeichen, einschließlich des NULL-Zeichens, das im Array zurückgegeben wird `szName` .</span><span class="sxs-lookup"><span data-stu-id="d33a8-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="d33a8-108">vorgenommen Ein Array, in dem der Name gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d33a8-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d33a8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d33a8-109">Remarks</span></span>  

 <span data-ttu-id="d33a8-110">Wenn ungleich `szName` NULL ist, kopiert die `GetName` Methode bis zu `cchName` Zeichen (einschließlich des NULL-Terminator) in `szName` .</span><span class="sxs-lookup"><span data-stu-id="d33a8-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="d33a8-111">Wenn ein nicht-NULL-Wert in zurückgegeben wird `pcchName` , wird die tatsächliche Anzahl von Zeichen im Namen (einschließlich des NULL-Abschluss Zeichens) im- `szName` Array gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d33a8-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="d33a8-112">Die- `GetName` Methode gibt eine S_OK HRESULT zurück, unabhängig davon, wie viele Zeichen kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d33a8-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d33a8-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d33a8-113">Requirements</span></span>  

 <span data-ttu-id="d33a8-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d33a8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d33a8-115">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="d33a8-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d33a8-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d33a8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d33a8-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d33a8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33a8-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d33a8-118">See also</span></span>

- [<span data-ttu-id="d33a8-119">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d33a8-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
