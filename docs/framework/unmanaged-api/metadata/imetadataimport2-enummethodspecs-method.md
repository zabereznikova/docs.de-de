---
title: IMetaDataImport2::EnumMethodSpecs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 4a1de144163ec2b4952bd16b59fb1c92b706631b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428296"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="ad88c-102">IMetaDataImport2::EnumMethodSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="ad88c-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="ad88c-103">Ruft einen Enumerator für ein Array von MethodSpec-Token ab, das mit dem angegebenen MethodDef-oder mitgliedsverweistoken verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ad88c-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad88c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad88c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ad88c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad88c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ad88c-106">[in, out] Ein Zeiger auf den Enumerator für `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="ad88c-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="ad88c-107">in Das mitgliedsverweis-oder MethodDef-Token, das die Methode darstellt, deren MethodSpec-Token aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ad88c-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="ad88c-108">Wenn der Wert von `tk` 0 (null) ist, werden alle MethodSpec-Token im Bereich aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ad88c-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="ad88c-109">vorgenommen Das Array von MethodSpec-Token, das aufgelistet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad88c-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ad88c-110">in Die angeforderte maximale Anzahl von Token, die in `rMethodSpecs`platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ad88c-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="ad88c-111">vorgenommen Die zurückgegebene Anzahl von Token, die in `rMethodSpecs`platziert werden.</span><span class="sxs-lookup"><span data-stu-id="ad88c-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad88c-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ad88c-112">Return Value</span></span>  
  
|<span data-ttu-id="ad88c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad88c-113">HRESULT</span></span>|<span data-ttu-id="ad88c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad88c-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ad88c-115">`EnumMethodSpecs` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad88c-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ad88c-116">`phEnum` hat keine Member-Elemente.</span><span class="sxs-lookup"><span data-stu-id="ad88c-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="ad88c-117">In diesem Fall wird `pcMethodSpecs` auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ad88c-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad88c-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ad88c-118">Requirements</span></span>  
 <span data-ttu-id="ad88c-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad88c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad88c-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ad88c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad88c-121">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad88c-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad88c-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad88c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad88c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad88c-123">See also</span></span>

- [<span data-ttu-id="ad88c-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad88c-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="ad88c-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad88c-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
