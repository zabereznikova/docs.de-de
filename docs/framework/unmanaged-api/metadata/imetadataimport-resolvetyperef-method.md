---
title: IMetaDataImport::ResolveTypeRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
ms.openlocfilehash: 800b15bb75e74898cee9d838900ea14b60620940
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431470"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="f554b-102">IMetaDataImport::ResolveTypeRef-Methode</span><span class="sxs-lookup"><span data-stu-id="f554b-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="f554b-103">Löst einen <xref:System.Type> Verweis auf, der durch das angegebene TypeRef-Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f554b-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f554b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f554b-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f554b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f554b-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="f554b-106">in Das TypeRef-Metadatentoken zum Zurückgeben der referenzierten Typinformationen für.</span><span class="sxs-lookup"><span data-stu-id="f554b-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="f554b-107">in Die IID der Schnittstelle, die in `ppIScope`zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="f554b-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="f554b-108">Dies wäre in der Regel IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="f554b-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="f554b-109">vorgenommen Eine Schnittstelle zum Modul Bereich, in dem der referenzierte Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f554b-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="f554b-110">vorgenommen Ein Zeiger auf ein TypeDef-Token, das den referenzierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="f554b-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f554b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f554b-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f554b-112">Verwenden Sie diese Methode nicht, wenn mehrere Anwendungs Domänen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f554b-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="f554b-113">Die-Methode respektiert Anwendungs Domänen Grenzen nicht.</span><span class="sxs-lookup"><span data-stu-id="f554b-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="f554b-114">Wenn mehrere Versionen einer Assembly geladen werden und der gleiche Typ mit demselben Namespace enthalten ist, gibt die Methode den Modul Bereich des ersten gefundenen Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="f554b-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="f554b-115">Die `ResolveTypeRef`-Methode sucht in anderen Modulen nach der Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="f554b-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="f554b-116">Wenn die Typdefinition gefunden wird, gibt `ResolveTypeRef` eine Schnittstelle zu diesem Modul Bereich und das TypeDef-Token für den Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="f554b-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="f554b-117">Wenn der zu lösende Typverweis einen Auflösungs Bereich von AssemblyRef hat, sucht die `ResolveTypeRef`-Methode nur in den Metadatenbereichen, die bereits mit Aufrufen der [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode oder der [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) -Methode geöffnet wurden, nach einer Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="f554b-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="f554b-118">Dies liegt daran, dass `ResolveTypeRef` nicht nur aus dem Bereich "AssemblyRef" ermitteln kann, in dem die Assembly auf der Festplatte oder im globalen Assemblycache gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f554b-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f554b-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f554b-119">Requirements</span></span>  
 <span data-ttu-id="f554b-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f554b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f554b-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f554b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f554b-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f554b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f554b-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f554b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f554b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f554b-124">See also</span></span>

- [<span data-ttu-id="f554b-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f554b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f554b-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f554b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
