---
title: IMetaDataImport::GetMemberRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: a61254ba751e47b0089a3f7528aca337a32e2db3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175368"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="44de3-102">IMetaDataImport::GetMemberRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="44de3-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="44de3-103">Ruft Metadaten ab, die dem Element zugeordnet sind, auf das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="44de3-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44de3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44de3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44de3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44de3-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="44de3-106">[in] Das MemberRef-Token, für das zugeordnete Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44de3-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="44de3-107">[out] Ein TypeDef- oder TypeRef- oder TypeSpec-Token, das die Klasse darstellt, die den Member deklariert, oder ein ModuleRef-Token, das die Modulklasse darstellt, die den Member deklariert, oder ein MethodDef, das den Member darstellt.</span><span class="sxs-lookup"><span data-stu-id="44de3-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="44de3-108">[out] Ein Zeichenfolgenpuffer für den Namen des Elements.</span><span class="sxs-lookup"><span data-stu-id="44de3-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="44de3-109">[in] Die angeforderte Größe `szMember`in breiten Zeichen von .</span><span class="sxs-lookup"><span data-stu-id="44de3-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="44de3-110">[out] Die zurückgegebene Größe `szMember`in breiten Zeichen von .</span><span class="sxs-lookup"><span data-stu-id="44de3-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="44de3-111">[out] Ein Zeiger auf die binäre Metadatensignatur für das Element.</span><span class="sxs-lookup"><span data-stu-id="44de3-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="44de3-112">[out] Die Größe in `ppvSigBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="44de3-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44de3-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="44de3-113">Requirements</span></span>  
 <span data-ttu-id="44de3-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44de3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44de3-115">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="44de3-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44de3-116">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="44de3-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44de3-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44de3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44de3-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44de3-118">See also</span></span>

- [<span data-ttu-id="44de3-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44de3-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="44de3-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44de3-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
