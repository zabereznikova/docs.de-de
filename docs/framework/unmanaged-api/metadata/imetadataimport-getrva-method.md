---
title: IMetaDataImport::GetRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 126cc9d407e2653fdb3f4ea7b03fa05c24a572d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629116"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="49376-102">IMetaDataImport::GetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="49376-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="49376-103">Ruft ab, die relative virtuelle Adresse (RVA) sowie die Implementierung der Methode oder des Felds, die durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="49376-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49376-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49376-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49376-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49376-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="49376-106">[in] Ein MethodDef oder FieldDef Metadatentoken, das die RVA für zurückzugebenden Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="49376-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="49376-107">Wenn das Token ein FieldDef ist, muss das Feld eine globale Variable sein.</span><span class="sxs-lookup"><span data-stu-id="49376-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="49376-108">[out] Ein Zeiger auf die relative virtuelle Adresse der vom Token dargestellten Codeobjekts.</span><span class="sxs-lookup"><span data-stu-id="49376-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="49376-109">[out] Ein Zeiger auf die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="49376-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="49376-110">Dieser Wert ist eine Bitmaske aus der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="49376-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="49376-111">Der Wert des `pdwImplFlags` gilt nur, wenn `tk` ist ein MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="49376-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49376-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49376-112">Requirements</span></span>  
 <span data-ttu-id="49376-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49376-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49376-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49376-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49376-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="49376-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49376-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49376-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49376-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49376-117">See also</span></span>
- [<span data-ttu-id="49376-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49376-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="49376-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49376-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
