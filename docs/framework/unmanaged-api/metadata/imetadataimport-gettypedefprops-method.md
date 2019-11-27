---
title: IMetaDataImport::GetTypeDefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: c9ac624e17223def206e86fd92ee4fd2de7f6082
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436751"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="ffee4-102">IMetaDataImport::GetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="ffee4-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="ffee4-103">Gibt Metadateninformationen für die <xref:System.Type> zurück, die durch das angegebene TypeDef-Token dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ffee4-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffee4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ffee4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffee4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ffee4-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ffee4-106">in Das TypeDef-Token, das den Typ darstellt, für den Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ffee4-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="ffee4-107">vorgenommen Ein Puffer, der den Typnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="ffee4-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="ffee4-108">in Die Größe in breit Zeichen `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="ffee4-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="ffee4-109">vorgenommen Die Anzahl der breit Zeichen, die in `szTypeDef`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ffee4-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="ffee4-110">vorgenommen Ein Zeiger auf alle Flags, die die Typdefinition ändern.</span><span class="sxs-lookup"><span data-stu-id="ffee4-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="ffee4-111">Dieser Wert ist eine Bitmaske aus der [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ffee4-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="ffee4-112">vorgenommen Ein TypeDef-oder TypeRef-Metadatentoken, das den Basistyp des angeforderten Typs darstellt.</span><span class="sxs-lookup"><span data-stu-id="ffee4-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffee4-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ffee4-113">Requirements</span></span>  
 <span data-ttu-id="ffee4-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffee4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffee4-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ffee4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ffee4-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ffee4-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ffee4-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffee4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffee4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffee4-118">See also</span></span>

- [<span data-ttu-id="ffee4-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffee4-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ffee4-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffee4-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
