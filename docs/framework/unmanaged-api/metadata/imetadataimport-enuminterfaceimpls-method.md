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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d0f94949cdc82cdecd52f003f3400c43014fabf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780460"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="98715-102">IMetaDataImport::EnumInterfaceImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="98715-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="98715-103">Listet alle Schnittstellen implementiert, mit dem angegebenen `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="98715-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="98715-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98715-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98715-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="98715-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="98715-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="98715-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="98715-107">[in] Das Token der TypeDef, die schnittstellenimplementierungen darstellen, deren MethodDef-Token sind, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="98715-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="98715-108">[out] Das Array zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="98715-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="98715-109">[in] Die maximale Größe des `rImpls`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="98715-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="98715-110">[out] Die tatsächliche Anzahl der in zurückgegebenen Token `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="98715-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98715-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="98715-111">Return Value</span></span>  
  
|<span data-ttu-id="98715-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98715-112">HRESULT</span></span>|<span data-ttu-id="98715-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98715-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="98715-114">`EnumInterfaceImpls` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98715-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="98715-115">Es sind keine MethodDef-Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="98715-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="98715-116">In diesem Fall `pcImpls` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="98715-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="98715-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98715-117">Remarks</span></span>

<span data-ttu-id="98715-118">Die Enumeration gibt eine Auflistung von `mdInterfaceImpl` -Token für jede Schnittstelle implementiert, mit dem angegebenen `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="98715-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="98715-119">Interface-Token in der Reihenfolge, die die Schnittstellen angegeben wurden. zurückgegeben werden (über `DefineTypeDef` oder `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="98715-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="98715-120">Eigenschaften des zurückgegebenen `mdInterfaceImpl` Token können abgefragt werden, mithilfe von [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="98715-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="98715-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98715-121">Requirements</span></span>  
 <span data-ttu-id="98715-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98715-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98715-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="98715-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98715-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="98715-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98715-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98715-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98715-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98715-126">See also</span></span>

- [<span data-ttu-id="98715-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98715-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="98715-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98715-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
