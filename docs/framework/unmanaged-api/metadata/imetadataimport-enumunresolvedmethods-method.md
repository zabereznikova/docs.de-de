---
title: IMetaDataImport::EnumUnresolvedMethods-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: c991c0af845bc6825db6b3bf258fe0809d5db804
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503695"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="4218d-102">IMetaDataImport::EnumUnresolvedMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="4218d-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="4218d-103">Zählt MemberDef-Token auf, die die nicht aufgelösten Methoden im aktuellen Metadatenbereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="4218d-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4218d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4218d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4218d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4218d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4218d-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="4218d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4218d-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="4218d-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="4218d-108">vorgenommen Das Array, das zum Speichern der mitgliedungstokentoken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4218d-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4218d-109">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="4218d-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4218d-110">vorgenommen Die Anzahl der in zurückgegebenen mitgliedungstokentoken `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="4218d-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4218d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4218d-111">Return Value</span></span>  
  
|<span data-ttu-id="4218d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4218d-112">HRESULT</span></span>|<span data-ttu-id="4218d-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4218d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4218d-114">`EnumUnresolvedMethods`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4218d-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4218d-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4218d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4218d-116">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="4218d-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4218d-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4218d-117">Remarks</span></span>  
 <span data-ttu-id="4218d-118">Eine nicht aufgelöste Methode ist eine Methode, die deklariert, aber nicht implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4218d-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="4218d-119">Eine-Methode ist in der-Enumeration enthalten, wenn die-Methode gekennzeichnet ist `miForwardRef` und entweder `mdPinvokeImpl` oder `miRuntime` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4218d-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="4218d-120">Anders ausgedrückt: eine nicht aufgelöste Methode ist eine Klassenmethode, die zwar markiert ist, `miForwardRef` aber nicht in nicht verwaltetem Code implementiert ist (über PInvoke erreicht) und intern von der Laufzeit selbst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="4218d-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="4218d-121">Die-Enumeration schließt alle Methoden aus, die entweder im Modul Bereich (Globals) oder in Schnittstellen oder abstrakten Klassen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="4218d-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4218d-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4218d-122">Requirements</span></span>  
 <span data-ttu-id="4218d-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4218d-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4218d-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4218d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4218d-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4218d-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4218d-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4218d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4218d-127">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="4218d-127">See also</span></span>

- [<span data-ttu-id="4218d-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4218d-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4218d-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4218d-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
