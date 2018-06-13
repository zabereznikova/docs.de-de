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
ms.openlocfilehash: 1232e8c574f263f709a9b66c7b1b3d06cca5e4da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447210"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="ab32d-102">IMetaDataImport::GetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="ab32d-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="ab32d-103">Ruft die relative virtuelle Adresse (RVA) sowie die Implementierung der Methode oder des Felds, die durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ab32d-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab32d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab32d-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab32d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab32d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ab32d-106">[in] Ein MethodDef oder FieldDef Metadatentoken, das die RVA für zurückzugebenden Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="ab32d-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="ab32d-107">Wenn das Token ein FieldDef ist, muss das Feld eine globale Variable sein.</span><span class="sxs-lookup"><span data-stu-id="ab32d-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="ab32d-108">[out] Ein Zeiger auf die relative virtuelle Adresse des vom Token dargestellten Codeobjekts.</span><span class="sxs-lookup"><span data-stu-id="ab32d-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="ab32d-109">[out] Ein Zeiger auf die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="ab32d-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="ab32d-110">Dieser Wert ist eine Bitmaske aus der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ab32d-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="ab32d-111">Der Wert der `pdwImplFlags` gilt nur, wenn `tk` ist ein MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="ab32d-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab32d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab32d-112">Requirements</span></span>  
 <span data-ttu-id="ab32d-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab32d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab32d-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ab32d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab32d-115">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ab32d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab32d-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab32d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab32d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab32d-117">See Also</span></span>  
 [<span data-ttu-id="ab32d-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab32d-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ab32d-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab32d-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
