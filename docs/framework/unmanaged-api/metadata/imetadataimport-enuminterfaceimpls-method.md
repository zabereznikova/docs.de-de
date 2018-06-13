---
title: IMetaDataImport::EnumInterfaceImpls-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447455"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="40e80-102">IMetaDataImport::EnumInterfaceImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="40e80-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="40e80-103">Zählt MethodDef-Token auf, die Schnittstellenimplementierungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="40e80-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e80-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40e80-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40e80-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40e80-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="40e80-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="40e80-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="40e80-107">[in] Das Token der TypeDef, die schnittstellenimplementierungen darstellen, deren MethodDef-Token werden aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="40e80-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="40e80-108">[out] Das Array zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40e80-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="40e80-109">[in] Die maximale Größe des `rImpls`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="40e80-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="40e80-110">[out] Die tatsächliche Anzahl der im zurückgegebenen Token `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="40e80-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40e80-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="40e80-111">Return Value</span></span>  
  
|<span data-ttu-id="40e80-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40e80-112">HRESULT</span></span>|<span data-ttu-id="40e80-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40e80-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="40e80-114">`EnumInterfaceImpls` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40e80-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="40e80-115">Es sind keine MethodDef-Token, aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="40e80-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="40e80-116">In diesem Fall `pcImpls` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="40e80-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40e80-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40e80-117">Requirements</span></span>  
 <span data-ttu-id="40e80-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40e80-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e80-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="40e80-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40e80-120">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="40e80-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40e80-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e80-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e80-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40e80-122">See Also</span></span>  
 [<span data-ttu-id="40e80-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40e80-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="40e80-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40e80-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
