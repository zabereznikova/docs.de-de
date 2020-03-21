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
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175381"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="9f7a0-102">IMetaDataImport::GetInterfaceImplProps-Methode</span><span class="sxs-lookup"><span data-stu-id="9f7a0-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="9f7a0-103">Ruft einen Zeiger auf die Metadatentoken für die ab, die <xref:System.Type> die angegebene Methode implementiert, und für die Schnittstelle, die diese Methode deklariert.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="9f7a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f7a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f7a0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f7a0-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="9f7a0-106">[in] Das Metadatentoken, das die Methode darstellt, für die die Klassen- und Schnittstellentoken zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="9f7a0-107">[out] Das Metadatentoken, das die Klasse darstellt, die die Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="9f7a0-108">[out] Das Metadatentoken, das die Schnittstelle darstellt, die die implementierte Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="9f7a0-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9f7a0-109">Remarks</span></span>

 <span data-ttu-id="9f7a0-110">Sie erhalten den `iImpl` Wert für, indem Sie die [EnumInterfaceImpls-Methode](imetadataimport-enuminterfaceimpls-method.md) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="9f7a0-111">Angenommen, eine Klasse hat `mdTypeDef` den Tokenwert 0x02000007 und implementiert drei Schnittstellen, deren Typen Token haben:</span><span class="sxs-lookup"><span data-stu-id="9f7a0-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="9f7a0-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="9f7a0-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="9f7a0-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="9f7a0-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="9f7a0-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="9f7a0-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="9f7a0-115">Diese Informationen werden konzeptionell in einer Schnittstellenimplementierungstabelle gespeichert als:</span><span class="sxs-lookup"><span data-stu-id="9f7a0-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="9f7a0-116">Zeilennummer</span><span class="sxs-lookup"><span data-stu-id="9f7a0-116">Row number</span></span> | <span data-ttu-id="9f7a0-117">Klassentoken</span><span class="sxs-lookup"><span data-stu-id="9f7a0-117">Class token</span></span> | <span data-ttu-id="9f7a0-118">Schnittstellentoken</span><span class="sxs-lookup"><span data-stu-id="9f7a0-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="9f7a0-119">4</span><span class="sxs-lookup"><span data-stu-id="9f7a0-119">4</span></span>          |             |                 |
| <span data-ttu-id="9f7a0-120">5</span><span class="sxs-lookup"><span data-stu-id="9f7a0-120">5</span></span>          | <span data-ttu-id="9f7a0-121">02000007</span><span class="sxs-lookup"><span data-stu-id="9f7a0-121">02000007</span></span>    | <span data-ttu-id="9f7a0-122">02000003</span><span class="sxs-lookup"><span data-stu-id="9f7a0-122">02000003</span></span>        |
| <span data-ttu-id="9f7a0-123">6</span><span class="sxs-lookup"><span data-stu-id="9f7a0-123">6</span></span>          | <span data-ttu-id="9f7a0-124">02000007</span><span class="sxs-lookup"><span data-stu-id="9f7a0-124">02000007</span></span>    | <span data-ttu-id="9f7a0-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="9f7a0-125">0100000A</span></span>        |
| <span data-ttu-id="9f7a0-126">7</span><span class="sxs-lookup"><span data-stu-id="9f7a0-126">7</span></span>          |             |                 |
| <span data-ttu-id="9f7a0-127">8</span><span class="sxs-lookup"><span data-stu-id="9f7a0-127">8</span></span>          | <span data-ttu-id="9f7a0-128">02000007</span><span class="sxs-lookup"><span data-stu-id="9f7a0-128">02000007</span></span>    | <span data-ttu-id="9f7a0-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="9f7a0-129">0200001C</span></span>        |

<span data-ttu-id="9f7a0-130">Rückruf, das Token ist ein 4-Byte-Wert:</span><span class="sxs-lookup"><span data-stu-id="9f7a0-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="9f7a0-131">Die unteren 3 Bytes enthalten die Zeilennummer oder RID.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="9f7a0-132">Das obere Byte enthält den Tokentyp `mdtInterfaceImpl`– 0x09 für .</span><span class="sxs-lookup"><span data-stu-id="9f7a0-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="9f7a0-133">`GetInterfaceImplProps`gibt die in der Zeile gehaltenen `iImpl` Informationen zurück, deren Token Sie im Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="9f7a0-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9f7a0-134">Requirements</span></span>  
 <span data-ttu-id="9f7a0-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f7a0-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f7a0-136">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9f7a0-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f7a0-137">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9f7a0-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f7a0-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f7a0-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f7a0-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f7a0-139">See also</span></span>

- [<span data-ttu-id="9f7a0-140">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f7a0-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9f7a0-141">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f7a0-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
