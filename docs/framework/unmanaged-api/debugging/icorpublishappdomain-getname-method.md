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
ms.openlocfilehash: 4325d61d12a66b17f88e5e368cbbc7806d0a3ec5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790705"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="08c88-102">ICorPublishAppDomain::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="08c88-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="08c88-103">Ruft den Namen der Anwendungsdomäne ab, die von dieser [ICorPublishAppDomain](icorpublishappdomain-interface.md)dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="08c88-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08c88-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08c88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08c88-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="08c88-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="08c88-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="08c88-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="08c88-107">vorgenommen Ein Zeiger auf die Anzahl der breit Zeichen, einschließlich des NULL-Zeichens, die im `szName` Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="08c88-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="08c88-108">vorgenommen Ein Array, in dem der Name gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="08c88-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08c88-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08c88-109">Remarks</span></span>  
 <span data-ttu-id="08c88-110">Wenn `szName` ungleich NULL ist, kopiert die Methode `GetName` bis zu `cchName` Zeichen (einschließlich des NULL-Terminator) in `szName`.</span><span class="sxs-lookup"><span data-stu-id="08c88-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="08c88-111">Wenn ein nicht-NULL-Wert in `pcchName`zurückgegeben wird, wird die tatsächliche Anzahl der Zeichen im Namen (einschließlich des NULL-Terminator) im `szName` Array gespeichert.</span><span class="sxs-lookup"><span data-stu-id="08c88-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="08c88-112">Die `GetName`-Methode gibt eine S_OK HRESULT zurück, unabhängig davon, wie viele Zeichen kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="08c88-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08c88-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08c88-113">Requirements</span></span>  
 <span data-ttu-id="08c88-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08c88-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08c88-115">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="08c88-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="08c88-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08c88-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08c88-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08c88-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c88-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08c88-118">See also</span></span>

- [<span data-ttu-id="08c88-119">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08c88-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
