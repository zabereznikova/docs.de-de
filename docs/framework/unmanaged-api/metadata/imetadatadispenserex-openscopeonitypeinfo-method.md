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
ms.openlocfilehash: 8deefe026e32a56d853e173e6a8fa3be942ccd9c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431134"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="6db6c-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="6db6c-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="6db6c-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="6db6c-103">This method is not implemented.</span></span> <span data-ttu-id="6db6c-104">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6db6c-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db6c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6db6c-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6db6c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6db6c-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="6db6c-107">in Ein Zeiger auf eine [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) -Schnittstelle, die die Typinformationen bereitstellt, für die der Bereich geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6db6c-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="6db6c-108">in Die Open Mode-Flags.</span><span class="sxs-lookup"><span data-stu-id="6db6c-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="6db6c-109">in Die gewünschte Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6db6c-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="6db6c-110">vorgenommen Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6db6c-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6db6c-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6db6c-111">Requirements</span></span>  
 <span data-ttu-id="6db6c-112">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6db6c-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6db6c-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6db6c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6db6c-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="6db6c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6db6c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6db6c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db6c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6db6c-116">See also</span></span>

- [<span data-ttu-id="6db6c-117">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6db6c-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="6db6c-118">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6db6c-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
