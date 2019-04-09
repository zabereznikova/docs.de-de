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
ms.openlocfilehash: a2c431abb7a4a872454b9c2689ee195ed36ef236
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177008"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="dc678-102">IMetaDataImport::GetMemberRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="dc678-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="dc678-103">Ruft Metadaten ab, die dem Element zugeordnet sind, auf das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dc678-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc678-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc678-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="dc678-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc678-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="dc678-106">[in] Das MemberRef-Token für die zugeordneten Metadaten zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="dc678-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="dc678-107">[out] Eine TypeDef oder TypeRef oder TypeSpec-Token, die die Klasse, die deklariert darstellt, das Element oder ein ModuleRef-Token, das die Modulklasse darstellt, die deklariert, das Element oder ein MethodDef, der den Member darstellt.</span><span class="sxs-lookup"><span data-stu-id="dc678-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="dc678-108">[out] Einen Zeichenfolgenpuffer für den Namen des Mitglieds.</span><span class="sxs-lookup"><span data-stu-id="dc678-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="dc678-109">[in] Die angeforderte Größe in Breitzeichen `szMember`.</span><span class="sxs-lookup"><span data-stu-id="dc678-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="dc678-110">[out] Die zurückgegebene Größe in Breitzeichen `szMember`.</span><span class="sxs-lookup"><span data-stu-id="dc678-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="dc678-111">[out] Ein Zeiger auf die binäre Metadatensignatur für das Element.</span><span class="sxs-lookup"><span data-stu-id="dc678-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="dc678-112">[out] Die Größe in Bytes der `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="dc678-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc678-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc678-113">Requirements</span></span>  
 <span data-ttu-id="dc678-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc678-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc678-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dc678-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc678-116">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dc678-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="dc678-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="dc678-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dc678-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc678-118">See also</span></span>

- [<span data-ttu-id="dc678-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc678-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dc678-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc678-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
