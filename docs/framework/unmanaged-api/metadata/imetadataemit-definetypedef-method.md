---
title: IMetaDataEmit::DefineTypeDef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: dc064b00e32bb6b1d8c2d0c20f571b35919eae23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009339"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="12b9c-102">IMetaDataEmit::DefineTypeDef-Methode</span><span class="sxs-lookup"><span data-stu-id="12b9c-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="12b9c-103">Erstellt eine Typdefinition für einen Common Language Runtime Typ und ruft ein Metadatentoken für diese Typdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="12b9c-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12b9c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12b9c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="12b9c-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="12b9c-106">in Der Name des Typs in Unicode.</span><span class="sxs-lookup"><span data-stu-id="12b9c-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="12b9c-107">[in] `TypeDef` legt.</span><span class="sxs-lookup"><span data-stu-id="12b9c-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="12b9c-108">Dies ist eine Bitmaske von `CoreTypeAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="12b9c-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="12b9c-109">in Das Token der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="12b9c-109">[in] The token of the base class.</span></span> <span data-ttu-id="12b9c-110">Dabei muss es sich entweder um ein- `mdTypeDef` oder ein- `mdTypeRef` Token handeln.</span><span class="sxs-lookup"><span data-stu-id="12b9c-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="12b9c-111">in Ein Array von-Token, das die Schnittstellen angibt, die diese Klasse oder Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="12b9c-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="12b9c-112">vorgenommen Das `mdTypeDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="12b9c-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12b9c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12b9c-113">Remarks</span></span>  
 <span data-ttu-id="12b9c-114">Ein Flag in `dwTypeDefFlags` gibt an, ob der erstellte Typ ein allgemeiner Typsystem-Verweistyp (Klasse oder Schnittstelle) oder ein allgemeiner Typsystem-Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="12b9c-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="12b9c-115">Abhängig von den angegebenen Parametern kann diese Methode als Nebeneffekt auch einen `mdInterfaceImpl` Datensatz für jede Schnittstelle erstellen, die von diesem Typ geerbt oder implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="12b9c-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="12b9c-116">Diese Methode gibt jedoch keines dieser `mdInterfaceImpl` Token zurück.</span><span class="sxs-lookup"><span data-stu-id="12b9c-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="12b9c-117">Wenn ein Client später ein Token hinzufügen oder ändern möchte `mdInterfaceImpl` , muss er die- `IMetaDataImport` Schnittstelle verwenden, um Sie zu auflisten.</span><span class="sxs-lookup"><span data-stu-id="12b9c-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="12b9c-118">Wenn Sie die com-Semantik der- `[default]` Schnittstelle verwenden möchten, sollten Sie die Standardschnittstelle als erstes Element in angeben `rtkImplements` . ein benutzerdefiniertes Attribut, das für die Klasse festgelegt ist, gibt an, dass die Klasse über eine Standardschnittstelle verfügt (bei der es sich immer um das erste Token handelt, das `mdInterfaceImpl` für die Klasse deklariert wurde).</span><span class="sxs-lookup"><span data-stu-id="12b9c-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="12b9c-119">Jedes Element des `rtkImplements` Arrays enthält ein- `mdTypeDef` oder- `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="12b9c-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="12b9c-120">Das letzte Element im Array muss sein `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="12b9c-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12b9c-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="12b9c-121">Requirements</span></span>  
 <span data-ttu-id="12b9c-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12b9c-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12b9c-123">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="12b9c-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12b9c-124">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="12b9c-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12b9c-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12b9c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b9c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12b9c-126">See also</span></span>

- [<span data-ttu-id="12b9c-127">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12b9c-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="12b9c-128">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12b9c-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
