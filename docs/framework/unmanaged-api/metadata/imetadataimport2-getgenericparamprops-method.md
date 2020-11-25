---
title: IMetaDataImport2::GetGenericParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 16f69d571ffed87a2e848124ce16ac942d319c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702679"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="f20b0-102">IMetaDataImport2::GetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="f20b0-102">IMetaDataImport2::GetGenericParamProps Method</span></span>

<span data-ttu-id="f20b0-103">Ruft die Metadaten ab, die dem durch das angegebene Token dargestellten generischen Parameter zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f20b0-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f20b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f20b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f20b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f20b0-105">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="f20b0-106">in Das Token, das den generischen Parameter darstellt, für den Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f20b0-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="f20b0-107">vorgenommen Die Ordinalposition des `Type` Parameters im übergeordneten Konstruktor oder in der Methode.</span><span class="sxs-lookup"><span data-stu-id="f20b0-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="f20b0-108">vorgenommen Ein Wert der [CorGenericParamAttr](corgenericparamattr-enumeration.md) -Enumeration, der die `Type` für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="f20b0-108">[out] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="f20b0-109">vorgenommen Ein TypeDef-oder MethodDef-Token, das den Besitzer des Parameters darstellt.</span><span class="sxs-lookup"><span data-stu-id="f20b0-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="f20b0-110">vorgenommen Reserviert für zukünftige Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="f20b0-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="f20b0-111">vorgenommen Der Name des generischen Parameters.</span><span class="sxs-lookup"><span data-stu-id="f20b0-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f20b0-112">in Die Größe des `wzName` Puffers.</span><span class="sxs-lookup"><span data-stu-id="f20b0-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f20b0-113">vorgenommen Die zurückgegebene Größe des Namens in breit Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f20b0-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f20b0-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f20b0-114">Requirements</span></span>  

 <span data-ttu-id="f20b0-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f20b0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f20b0-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f20b0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f20b0-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="f20b0-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f20b0-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f20b0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f20b0-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f20b0-119">See also</span></span>

- [<span data-ttu-id="f20b0-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f20b0-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="f20b0-121">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f20b0-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
