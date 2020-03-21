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
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175498"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="0f310-102">IMetaDataImport::EnumInterfaceImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="0f310-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="0f310-103">Zählt alle Schnittstellen auf, die `TypeDef`von der angegebenen implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="0f310-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="0f310-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f310-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f310-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f310-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0f310-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="0f310-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="0f310-107">[in] Das Token der TypeDef, deren MethodDef-Token, die Schnittstellenimplementierungen darstellen, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0f310-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="0f310-108">[out] Das Array, das zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f310-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0f310-109">[in] Die maximale Länge `rImpls` des Arrays.</span><span class="sxs-lookup"><span data-stu-id="0f310-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="0f310-110">[out] Die tatsächliche Anzahl der `rImpls`Token, die in zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0f310-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f310-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f310-111">Return Value</span></span>  
  
|<span data-ttu-id="0f310-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f310-112">HRESULT</span></span>|<span data-ttu-id="0f310-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f310-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0f310-114">`EnumInterfaceImpls`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0f310-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0f310-115">Es sind keine MethodDef-Token zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0f310-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="0f310-116">In diesem `pcImpls` Fall ist auf Null gesetzt.</span><span class="sxs-lookup"><span data-stu-id="0f310-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="0f310-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0f310-117">Remarks</span></span>

<span data-ttu-id="0f310-118">Die Enumeration gibt `mdInterfaceImpl` eine Auflistung von Token für `TypeDef`jede Schnittstelle zurück, die von der angegebenen implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="0f310-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="0f310-119">Schnittstellentoken werden in der Reihenfolge zurückgegeben, in `DefineTypeDef` `SetTypeDefProps`der die Schnittstellen angegeben wurden (durch oder ).</span><span class="sxs-lookup"><span data-stu-id="0f310-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="0f310-120">Eigenschaften der `mdInterfaceImpl` zurückgegebenen Token können mit [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="0f310-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="0f310-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0f310-121">Requirements</span></span>  
 <span data-ttu-id="0f310-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f310-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f310-123">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f310-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f310-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0f310-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f310-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f310-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f310-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f310-126">See also</span></span>

- [<span data-ttu-id="0f310-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f310-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0f310-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f310-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
