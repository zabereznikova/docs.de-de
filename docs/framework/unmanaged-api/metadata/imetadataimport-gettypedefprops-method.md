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
ms.openlocfilehash: 6346b1e34e508e5c173bfd0119ac7451d7eef40e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490795"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="0a9a0-102">IMetaDataImport::GetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="0a9a0-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="0a9a0-103">Gibt Metadateninformationen für das zurück, das <xref:System.Type> durch das angegebene TypeDef-Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a9a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a9a0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0a9a0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a9a0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0a9a0-106">in Das TypeDef-Token, das den Typ darstellt, für den Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="0a9a0-107">vorgenommen Ein Puffer, der den Typnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="0a9a0-108">in Die Größe in breit Zeichen von `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="0a9a0-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="0a9a0-109">vorgenommen Die Anzahl der breit Zeichen, die in zurückgegeben werden `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="0a9a0-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="0a9a0-110">vorgenommen Ein Zeiger auf alle Flags, die die Typdefinition ändern.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="0a9a0-111">Dieser Wert ist eine Bitmaske aus der [CorTypeAttr](cortypeattr-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-111">This value is a bitmask from the [CorTypeAttr](cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="0a9a0-112">vorgenommen Ein TypeDef-oder TypeRef-Metadatentoken, das den Basistyp des angeforderten Typs darstellt.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a9a0-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0a9a0-113">Requirements</span></span>  
 <span data-ttu-id="0a9a0-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a9a0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a9a0-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0a9a0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a9a0-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0a9a0-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a9a0-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a9a0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9a0-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="0a9a0-118">See also</span></span>

- [<span data-ttu-id="0a9a0-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a9a0-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0a9a0-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a9a0-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
