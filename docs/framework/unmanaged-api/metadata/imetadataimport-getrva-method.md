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
ms.openlocfilehash: 58ab9ee9381fce4d7af1910df6c8d3bb813bcf13
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490890"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="c0ba9-102">IMetaDataImport::GetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ba9-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="c0ba9-103">Ruft die relative virtuelle Adresse (RVA) und die Implementierungsflags der Methode oder des Felds ab, die durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c0ba9-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ba9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0ba9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0ba9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0ba9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c0ba9-106">in Ein MethodDef-oder FieldDef-Metadatentoken, das das Code Objekt darstellt, für das die RVA zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0ba9-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="c0ba9-107">Wenn das Token ein FieldDef-Token ist, muss es sich bei dem Feld um eine globale Variable handeln.</span><span class="sxs-lookup"><span data-stu-id="c0ba9-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="c0ba9-108">vorgenommen Ein Zeiger auf die relative virtuelle Adresse des Code Objekts, das durch das Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c0ba9-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="c0ba9-109">vorgenommen Ein Zeiger auf die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="c0ba9-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="c0ba9-110">Dieser Wert ist eine Bitmaske aus der [CorMethodImpl](cormethodimpl-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c0ba9-110">This value is a bitmask from the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="c0ba9-111">Der Wert von `pdwImplFlags` ist nur gültig, wenn `tk` ein MethodDef-Token ist.</span><span class="sxs-lookup"><span data-stu-id="c0ba9-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ba9-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c0ba9-112">Requirements</span></span>  
 <span data-ttu-id="c0ba9-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ba9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ba9-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c0ba9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0ba9-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c0ba9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0ba9-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ba9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ba9-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c0ba9-117">See also</span></span>

- [<span data-ttu-id="c0ba9-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0ba9-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c0ba9-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0ba9-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
