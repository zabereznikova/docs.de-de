---
title: IMetaDataImport::EnumInterfaceImpls-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumInterfaceImpls
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d9f2883c32daafd8938bd1c80c035a3527cc6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="66ae0-102">IMetaDataImport::EnumInterfaceImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="66ae0-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="66ae0-103">Zählt MethodDef-Token auf, die Schnittstellenimplementierungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="66ae0-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66ae0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66ae0-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66ae0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66ae0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="66ae0-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="66ae0-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="66ae0-107">[in] Das Token der TypeDef, die schnittstellenimplementierungen darstellen, deren MethodDef-Token werden aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="66ae0-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="66ae0-108">[out] Das Array zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66ae0-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="66ae0-109">[in] Die maximale Größe des `rImpls`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="66ae0-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="66ae0-110">[out] Die tatsächliche Anzahl der im zurückgegebenen Token `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="66ae0-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66ae0-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="66ae0-111">Return Value</span></span>  
  
|<span data-ttu-id="66ae0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66ae0-112">HRESULT</span></span>|<span data-ttu-id="66ae0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66ae0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="66ae0-114">`EnumInterfaceImpls`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="66ae0-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="66ae0-115">Es sind keine MethodDef-Token, aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="66ae0-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="66ae0-116">In diesem Fall `pcImpls` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="66ae0-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66ae0-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66ae0-117">Requirements</span></span>  
 <span data-ttu-id="66ae0-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66ae0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66ae0-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66ae0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66ae0-120">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="66ae0-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66ae0-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66ae0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ae0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66ae0-122">See Also</span></span>  
 [<span data-ttu-id="66ae0-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66ae0-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="66ae0-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66ae0-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
