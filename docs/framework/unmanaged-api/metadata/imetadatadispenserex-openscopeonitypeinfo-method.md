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
ms.openlocfilehash: deecd9ed4161bbd72e97a6320188961ae76d1e7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218783"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="a84fb-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="a84fb-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="a84fb-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="a84fb-103">This method is not implemented.</span></span> <span data-ttu-id="a84fb-104">Wird aufgerufen, gibt E_NOTIMPL zurück.</span><span class="sxs-lookup"><span data-stu-id="a84fb-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a84fb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a84fb-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a84fb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a84fb-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="a84fb-107">[in] Zeiger auf ein [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) -Schnittstelle, die von die Typinformationen für die den Bereich geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a84fb-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a84fb-108">[in] Der Modus "open"-Flags.</span><span class="sxs-lookup"><span data-stu-id="a84fb-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="a84fb-109">[in] Die gewünschte Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a84fb-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="a84fb-110">[out] Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a84fb-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a84fb-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a84fb-111">Requirements</span></span>  
 <span data-ttu-id="a84fb-112">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a84fb-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a84fb-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a84fb-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a84fb-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a84fb-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a84fb-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a84fb-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a84fb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a84fb-116">See also</span></span>

- [<span data-ttu-id="a84fb-117">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a84fb-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="a84fb-118">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a84fb-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
