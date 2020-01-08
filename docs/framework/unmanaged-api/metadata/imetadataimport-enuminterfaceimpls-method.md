---
title: IMetaDataImport::EnumInterfaceImpls-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338066"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="b014c-102">IMetaDataImport::EnumInterfaceImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="b014c-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="b014c-103">Listet alle Schnittstellen auf, die durch die angegebene `TypeDef`implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="b014c-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b014c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b014c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b014c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b014c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b014c-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="b014c-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="b014c-107">in Das Token der typedef, dessen MethodDef-Token, die Schnittstellen Implementierungen darstellen, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b014c-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="b014c-108">vorgenommen Das Array, das zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b014c-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b014c-109">in Die maximale Länge des `rImpls` Arrays.</span><span class="sxs-lookup"><span data-stu-id="b014c-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="b014c-110">vorgenommen Die tatsächliche Anzahl von Token, die in `rImpls`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b014c-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b014c-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b014c-111">Return Value</span></span>  
  
|<span data-ttu-id="b014c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b014c-112">HRESULT</span></span>|<span data-ttu-id="b014c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b014c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b014c-114">`EnumInterfaceImpls` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b014c-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b014c-115">Es sind keine MethodDef-Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b014c-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="b014c-116">In diesem Fall wird `pcImpls` auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b014c-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="b014c-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b014c-117">Remarks</span></span>

<span data-ttu-id="b014c-118">Die-Enumeration gibt eine Auflistung von `mdInterfaceImpl`-Token für jede Schnittstelle zurück, die vom angegebenen `TypeDef`implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="b014c-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="b014c-119">Schnittstellen Token werden in der Reihenfolge zurückgegeben, in der die Schnittstellen angegeben wurden (über `DefineTypeDef` oder `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="b014c-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="b014c-120">Eigenschaften der zurückgegebenen `mdInterfaceImpl` Token können mithilfe von " [getinterfakeimplproperties](imetadataimport-getinterfaceimplprops-method.md)" abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="b014c-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="b014c-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b014c-121">Requirements</span></span>  
 <span data-ttu-id="b014c-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b014c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b014c-123">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b014c-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b014c-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b014c-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b014c-125">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b014c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b014c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b014c-126">See also</span></span>

- [<span data-ttu-id="b014c-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b014c-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b014c-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b014c-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
