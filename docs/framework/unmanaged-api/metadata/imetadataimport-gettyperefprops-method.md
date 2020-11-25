---
title: IMetaDataImport::GetTypeRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 5d98481d7934b4c96178aaa32fb0f9378eb359fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729167"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="b9932-102">IMetaDataImport::GetTypeRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="b9932-102">IMetaDataImport::GetTypeRefProps Method</span></span>

<span data-ttu-id="b9932-103">Ruft die Metadaten ab, die dem zugeordnet sind, <xref:System.Type> auf die vom angegebenen TypeRef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b9932-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9932-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9932-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9932-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9932-105">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="b9932-106">in Das TypeRef-Token, das den Typ darstellt, für den Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9932-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="b9932-107">vorgenommen Ein Zeiger auf den Bereich, in dem der Verweis erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b9932-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="b9932-108">Dieser Wert ist ein AssemblyRef-oder ModuleRef-Token.</span><span class="sxs-lookup"><span data-stu-id="b9932-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="b9932-109">vorgenommen Ein Puffer, der den Typnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="b9932-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b9932-110">in Die angeforderte Größe in breit Zeichen von `szName` .</span><span class="sxs-lookup"><span data-stu-id="b9932-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b9932-111">vorgenommen Die zurückgegebene Größe in breit Zeichen von `szName` .</span><span class="sxs-lookup"><span data-stu-id="b9932-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9932-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b9932-112">Requirements</span></span>  

 <span data-ttu-id="b9932-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9932-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9932-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9932-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9932-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b9932-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9932-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9932-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9932-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9932-117">See also</span></span>

- [<span data-ttu-id="b9932-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9932-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b9932-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9932-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
