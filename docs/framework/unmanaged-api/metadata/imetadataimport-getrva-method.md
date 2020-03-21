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
ms.openlocfilehash: 190bcacc84646cfd9294cf2b6b53b0474f38758f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177217"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="e3fae-102">IMetaDataImport::GetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="e3fae-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="e3fae-103">Ruft die relative virtuelle Adresse (RVA) und die Implementierungsflags der Methode oder des Felds ab, die durch das angegebene Token dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e3fae-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3fae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3fae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3fae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3fae-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e3fae-106">[in] Ein MethodDef- oder FieldDef-Metadatentoken, das das Codeobjekt darstellt, für das die RVA zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3fae-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="e3fae-107">Wenn es sich bei dem Token um ein FieldDef handelt, muss es sich bei dem Feld um eine globale Variable handelt.</span><span class="sxs-lookup"><span data-stu-id="e3fae-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="e3fae-108">[out] Ein Zeiger auf die relative virtuelle Adresse des Codeobjekts, das durch das Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e3fae-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="e3fae-109">[out] Ein Zeiger auf die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="e3fae-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="e3fae-110">Dieser Wert ist eine Bitmaske aus der [CorMethodImpl-Enumeration.](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="e3fae-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="e3fae-111">Der Wert `pdwImplFlags` von ist `tk` nur gültig, wenn es sich um ein MethodDef-Token handelt.</span><span class="sxs-lookup"><span data-stu-id="e3fae-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3fae-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e3fae-112">Requirements</span></span>  
 <span data-ttu-id="e3fae-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3fae-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3fae-114">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e3fae-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e3fae-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e3fae-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e3fae-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3fae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3fae-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3fae-117">See also</span></span>

- [<span data-ttu-id="e3fae-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3fae-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e3fae-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3fae-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
