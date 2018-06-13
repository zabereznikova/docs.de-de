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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d62b9be1bef16014e2870c15a232bb46d4daf10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448748"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="80ca4-102">IMetaDataImport::GetMemberRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="80ca4-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="80ca4-103">Ruft Metadaten ab, die dem Element zugeordnet sind, auf das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="80ca4-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ca4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80ca4-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="80ca4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="80ca4-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="80ca4-106">[in] Das MemberRef-Token für die zugeordneten Metadaten zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="80ca4-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="80ca4-107">[out] Eine TypeDef oder TypeRef-Token oder TypeSpec-Token, das die Klasse, die deklariert wird darstellt, das Element oder ein ModuleRef-Token, die Module-Klasse darstellt, die deklariert wird, das Element oder ein MethodDef, der das Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="80ca4-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="80ca4-108">[out] Einen Zeichenfolgenpuffer für der Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="80ca4-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="80ca4-109">[in] Die angeforderte Größe in Breitzeichen `szMember`.</span><span class="sxs-lookup"><span data-stu-id="80ca4-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="80ca4-110">[out] Die zurückgegebene Größe in Breitzeichen `szMember`.</span><span class="sxs-lookup"><span data-stu-id="80ca4-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="80ca4-111">[out] Ein Zeiger auf die binäre Metadatensignatur für das Element.</span><span class="sxs-lookup"><span data-stu-id="80ca4-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="80ca4-112">[out] Die Größe in Bytes des `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="80ca4-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80ca4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80ca4-113">Requirements</span></span>  
 <span data-ttu-id="80ca4-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80ca4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ca4-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="80ca4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80ca4-116">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="80ca4-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80ca4-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ca4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ca4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80ca4-118">See Also</span></span>  
 [<span data-ttu-id="80ca4-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80ca4-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="80ca4-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80ca4-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
