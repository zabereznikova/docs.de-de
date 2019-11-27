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
ms.openlocfilehash: 1d6d66ea62cbf679f722f830b3638455001aedd6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437489"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="13454-102">IMetaDataImport::GetMemberRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="13454-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="13454-103">Ruft Metadaten ab, die dem Element zugeordnet sind, auf das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="13454-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13454-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13454-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="13454-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13454-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="13454-106">in Das Element, für das die zugeordneten Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13454-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="13454-107">vorgenommen Ein TypeDef-oder TypeRef-oder TypeSpec-Token, das die Klasse darstellt, die den Member deklariert, oder ein ModuleRef-Token, das die Modul Klasse darstellt, die den Member deklariert, oder ein MethodDef-Token, das den Member darstellt.</span><span class="sxs-lookup"><span data-stu-id="13454-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="13454-108">vorgenommen Ein Zeichen folgen Puffer für den Namen des Members.</span><span class="sxs-lookup"><span data-stu-id="13454-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="13454-109">in Die angeforderte Größe in breit Zeichen `szMember`.</span><span class="sxs-lookup"><span data-stu-id="13454-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="13454-110">vorgenommen Die zurückgegebene Größe in breit Zeichen `szMember`.</span><span class="sxs-lookup"><span data-stu-id="13454-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="13454-111">vorgenommen Ein Zeiger auf die binäre Metadatensignatur für den Member.</span><span class="sxs-lookup"><span data-stu-id="13454-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="13454-112">vorgenommen Die Größe `ppvSigBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="13454-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13454-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="13454-113">Requirements</span></span>  
 <span data-ttu-id="13454-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13454-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13454-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="13454-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13454-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="13454-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13454-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13454-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13454-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13454-118">See also</span></span>

- [<span data-ttu-id="13454-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13454-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="13454-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13454-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
