---
title: IMetaDataImport::GetInterfaceImplProps-Methode
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e2ebbd47a5e36a722fce33ba67d7efb4db8675
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777766"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="02c7f-102">IMetaDataImport::GetInterfaceImplProps-Methode</span><span class="sxs-lookup"><span data-stu-id="02c7f-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="02c7f-103">Ruft einen Zeiger auf das Metadatentoken für die <xref:System.Type> , der die angegebene Methode implementiert und für die Schnittstelle, die diese Methode deklariert.</span><span class="sxs-lookup"><span data-stu-id="02c7f-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="02c7f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02c7f-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02c7f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="02c7f-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="02c7f-106">[in] Das Metadatentoken, das die Methode zum Zurückgeben von der Klassen- und Token für darstellt.</span><span class="sxs-lookup"><span data-stu-id="02c7f-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="02c7f-107">[out] Das Metadatentoken, das die Klasse, die Methode implementiert, darstellt.</span><span class="sxs-lookup"><span data-stu-id="02c7f-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="02c7f-108">[out] Das Metadatentoken, das die Schnittstelle, die die implementierte Methode definiert darstellt.</span><span class="sxs-lookup"><span data-stu-id="02c7f-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="02c7f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02c7f-109">Remarks</span></span>

 <span data-ttu-id="02c7f-110">Rufen Sie den Wert für `iImpl` durch Aufrufen der [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="02c7f-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="02c7f-111">Nehmen wir beispielsweise an, dass eine Klasse verfügt über eine `mdTypeDef` token-Wert von 0 x 02000007 und, dass es drei Schnittstellen implementiert, deren Typen Token haben:</span><span class="sxs-lookup"><span data-stu-id="02c7f-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="02c7f-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="02c7f-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="02c7f-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="02c7f-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="02c7f-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="02c7f-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="02c7f-115">Vom Konzept her ist diese Informationen in eine Schnittstellentabelle-Implementierung als gespeichert:</span><span class="sxs-lookup"><span data-stu-id="02c7f-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="02c7f-116">Zeilennummer</span><span class="sxs-lookup"><span data-stu-id="02c7f-116">Row number</span></span> | <span data-ttu-id="02c7f-117">Klassen-token</span><span class="sxs-lookup"><span data-stu-id="02c7f-117">Class token</span></span> | <span data-ttu-id="02c7f-118">Interface-token</span><span class="sxs-lookup"><span data-stu-id="02c7f-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="02c7f-119">4</span><span class="sxs-lookup"><span data-stu-id="02c7f-119">4</span></span>          |             |                 |
| <span data-ttu-id="02c7f-120">5</span><span class="sxs-lookup"><span data-stu-id="02c7f-120">5</span></span>          | <span data-ttu-id="02c7f-121">02000007</span><span class="sxs-lookup"><span data-stu-id="02c7f-121">02000007</span></span>    | <span data-ttu-id="02c7f-122">02000003</span><span class="sxs-lookup"><span data-stu-id="02c7f-122">02000003</span></span>        |
| <span data-ttu-id="02c7f-123">6</span><span class="sxs-lookup"><span data-stu-id="02c7f-123">6</span></span>          | <span data-ttu-id="02c7f-124">02000007</span><span class="sxs-lookup"><span data-stu-id="02c7f-124">02000007</span></span>    | <span data-ttu-id="02c7f-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="02c7f-125">0100000A</span></span>        |
| <span data-ttu-id="02c7f-126">7</span><span class="sxs-lookup"><span data-stu-id="02c7f-126">7</span></span>          |             |                 |
| <span data-ttu-id="02c7f-127">8</span><span class="sxs-lookup"><span data-stu-id="02c7f-127">8</span></span>          | <span data-ttu-id="02c7f-128">02000007</span><span class="sxs-lookup"><span data-stu-id="02c7f-128">02000007</span></span>    | <span data-ttu-id="02c7f-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="02c7f-129">0200001C</span></span>        |

<span data-ttu-id="02c7f-130">Denken Sie daran, das Token ein 4-Byte-Wert ist:</span><span class="sxs-lookup"><span data-stu-id="02c7f-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="02c7f-131">Die niederwertigen 3 Bytes enthalten die Nummer der Zeile, oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="02c7f-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="02c7f-132">Das obere Byte enthält den Tokentyp: 0 x 09 für `mdtInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="02c7f-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="02c7f-133">`GetInterfaceImplProps` Gibt die Informationen, in der Zeile, deren Token, das Sie bereitstellen gespeichert, in der `iImpl` Argument.</span><span class="sxs-lookup"><span data-stu-id="02c7f-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="02c7f-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02c7f-134">Requirements</span></span>  
 <span data-ttu-id="02c7f-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02c7f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c7f-136">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="02c7f-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02c7f-137">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="02c7f-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02c7f-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02c7f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c7f-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02c7f-139">See also</span></span>

- [<span data-ttu-id="02c7f-140">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02c7f-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="02c7f-141">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02c7f-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
