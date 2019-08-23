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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f323e91e60c9735a51e955eaab6673ca167f294d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951878"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="dbc86-102">IMetaDataImport::ResolveTypeRef-Methode</span><span class="sxs-lookup"><span data-stu-id="dbc86-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="dbc86-103">Löst einen <xref:System.Type> Verweis auf, der durch das angegebene TypeRef-Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="dbc86-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbc86-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbc86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbc86-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="dbc86-106">in Das TypeRef-Metadatentoken zum Zurückgeben der referenzierten Typinformationen für.</span><span class="sxs-lookup"><span data-stu-id="dbc86-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="dbc86-107">in Die IID der Schnittstelle, die in `ppIScope`zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="dbc86-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="dbc86-108">Normalerweise ist dies IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="dbc86-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="dbc86-109">vorgenommen Eine Schnittstelle zum Modul Bereich, in dem der referenzierte Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="dbc86-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="dbc86-110">vorgenommen Ein Zeiger auf ein TypeDef-Token, das den referenzierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="dbc86-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbc86-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbc86-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="dbc86-112">Verwenden Sie diese Methode nicht, wenn mehrere Anwendungs Domänen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="dbc86-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="dbc86-113">Die-Methode respektiert Anwendungs Domänen Grenzen nicht.</span><span class="sxs-lookup"><span data-stu-id="dbc86-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="dbc86-114">Wenn mehrere Versionen einer Assembly geladen werden und der gleiche Typ mit demselben Namespace enthalten ist, gibt die Methode den Modul Bereich des ersten gefundenen Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="dbc86-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="dbc86-115">Die `ResolveTypeRef` -Methode sucht in anderen Modulen nach der Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="dbc86-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="dbc86-116">Wenn die Typdefinition gefunden wird, `ResolveTypeRef` gibt eine Schnittstelle zu diesem Modul Bereich und das TypeDef-Token für den Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="dbc86-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="dbc86-117">Wenn der zu lösende Typverweis einen Auflösungs Bereich von AssemblyRef hat, sucht `ResolveTypeRef` die Methode nur nach einer Entsprechung in den Metadatenbereichen, die bereits mit Aufrufen der [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode geöffnet wurden, oder der [ IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="dbc86-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="dbc86-118">Dies liegt daran `ResolveTypeRef` , dass von nur der AssemblyRef-Bereich bestimmt werden kann, in dem die Assembly auf der Festplatte oder im globalen Assemblycache gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="dbc86-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbc86-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbc86-119">Requirements</span></span>  
 <span data-ttu-id="dbc86-120">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbc86-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbc86-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dbc86-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dbc86-122">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dbc86-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dbc86-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbc86-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc86-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbc86-124">See also</span></span>

- [<span data-ttu-id="dbc86-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbc86-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dbc86-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbc86-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
