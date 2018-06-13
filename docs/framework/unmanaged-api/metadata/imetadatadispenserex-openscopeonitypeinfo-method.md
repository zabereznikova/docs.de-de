---
title: IMetaDataDispenserEx::OpenScopeOnITypeInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73866ef2dc7069708887c128f977f730519603bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446022"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="96e58-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="96e58-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="96e58-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="96e58-103">This method is not implemented.</span></span> <span data-ttu-id="96e58-104">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96e58-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e58-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="96e58-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96e58-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="96e58-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="96e58-107">[in] Zeiger auf eine [ITypeInfo](http://msdn.microsoft.com/library/f3356463-3373-4279-bae1-953378aa2680) Schnittstelle, die die Typinformationen für das Öffnen des Bereichs bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="96e58-107">[in] Pointer to an [ITypeInfo](http://msdn.microsoft.com/library/f3356463-3373-4279-bae1-953378aa2680) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="96e58-108">[in] Die open-Modus-Flags.</span><span class="sxs-lookup"><span data-stu-id="96e58-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="96e58-109">[in] Die gewünschte Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="96e58-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="96e58-110">[out] Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="96e58-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96e58-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96e58-111">Requirements</span></span>  
 <span data-ttu-id="96e58-112">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96e58-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96e58-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="96e58-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96e58-114">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="96e58-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="96e58-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e58-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96e58-116">See Also</span></span>  
 [<span data-ttu-id="96e58-117">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96e58-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="96e58-118">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96e58-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
