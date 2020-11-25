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
ms.openlocfilehash: e81816ce2194c2c1862cb997ad2c6e5baf301231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703999"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="c447e-102">IMetaDataImport::GetInterfaceImplProps-Methode</span><span class="sxs-lookup"><span data-stu-id="c447e-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>

<span data-ttu-id="c447e-103">Ruft einen Zeiger auf die Metadatentoken für den ab, der <xref:System.Type> die angegebene Methode implementiert, und für die-Schnittstelle, die diese Methode deklariert.</span><span class="sxs-lookup"><span data-stu-id="c447e-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c447e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c447e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c447e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c447e-105">Parameters</span></span>  

 `iiImpl`  
 <span data-ttu-id="c447e-106">in Das Metadatentoken, das die Methode darstellt, für die die Klassen-und Schnittstellen Token zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c447e-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="c447e-107">vorgenommen Das Metadatentoken, das die Klasse darstellt, die die Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="c447e-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="c447e-108">vorgenommen Das Metadatentoken, das die Schnittstelle darstellt, die die implementierte Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="c447e-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="c447e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c447e-109">Remarks</span></span>

 <span data-ttu-id="c447e-110">Sie erhalten den Wert für, `iImpl` indem Sie die [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c447e-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="c447e-111">Nehmen wir beispielsweise an, dass eine Klasse einen `mdTypeDef` Tokenwert von 0x02000007 aufweist und drei Schnittstellen implementiert, deren Typen über Token verfügen:</span><span class="sxs-lookup"><span data-stu-id="c447e-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="c447e-112">0x02000003 (typedef)</span><span class="sxs-lookup"><span data-stu-id="c447e-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="c447e-113">0x0100000a (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="c447e-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="c447e-114">0x0200001c (typedef)</span><span class="sxs-lookup"><span data-stu-id="c447e-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="c447e-115">Konzeptionell werden diese Informationen in einer Schnittstellen Implementierungs Tabelle wie folgt gespeichert:</span><span class="sxs-lookup"><span data-stu-id="c447e-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="c447e-116">Zeilennummer</span><span class="sxs-lookup"><span data-stu-id="c447e-116">Row number</span></span> | <span data-ttu-id="c447e-117">Class-Token</span><span class="sxs-lookup"><span data-stu-id="c447e-117">Class token</span></span> | <span data-ttu-id="c447e-118">Schnittstellen Token</span><span class="sxs-lookup"><span data-stu-id="c447e-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="c447e-119">4</span><span class="sxs-lookup"><span data-stu-id="c447e-119">4</span></span>          |             |                 |
| <span data-ttu-id="c447e-120">5</span><span class="sxs-lookup"><span data-stu-id="c447e-120">5</span></span>          | <span data-ttu-id="c447e-121">02000007</span><span class="sxs-lookup"><span data-stu-id="c447e-121">02000007</span></span>    | <span data-ttu-id="c447e-122">02000003</span><span class="sxs-lookup"><span data-stu-id="c447e-122">02000003</span></span>        |
| <span data-ttu-id="c447e-123">6</span><span class="sxs-lookup"><span data-stu-id="c447e-123">6</span></span>          | <span data-ttu-id="c447e-124">02000007</span><span class="sxs-lookup"><span data-stu-id="c447e-124">02000007</span></span>    | <span data-ttu-id="c447e-125">0100000a</span><span class="sxs-lookup"><span data-stu-id="c447e-125">0100000A</span></span>        |
| <span data-ttu-id="c447e-126">7</span><span class="sxs-lookup"><span data-stu-id="c447e-126">7</span></span>          |             |                 |
| <span data-ttu-id="c447e-127">8</span><span class="sxs-lookup"><span data-stu-id="c447e-127">8</span></span>          | <span data-ttu-id="c447e-128">02000007</span><span class="sxs-lookup"><span data-stu-id="c447e-128">02000007</span></span>    | <span data-ttu-id="c447e-129">0200001c</span><span class="sxs-lookup"><span data-stu-id="c447e-129">0200001C</span></span>        |

<span data-ttu-id="c447e-130">Rückruf: das Token ist ein 4-Byte-Wert:</span><span class="sxs-lookup"><span data-stu-id="c447e-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="c447e-131">Die unteren 3 Bytes enthalten die Zeilennummer oder RID.</span><span class="sxs-lookup"><span data-stu-id="c447e-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="c447e-132">Das obere Byte enthält den Tokentyp – 0x09 für `mdtInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="c447e-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="c447e-133">`GetInterfaceImplProps` Gibt die in der Zeile gespeicherten Informationen zurück, deren Token Sie im- `iImpl` Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="c447e-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="c447e-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c447e-134">Requirements</span></span>  

 <span data-ttu-id="c447e-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c447e-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c447e-136">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c447e-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c447e-137">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c447e-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c447e-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c447e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c447e-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c447e-139">See also</span></span>

- [<span data-ttu-id="c447e-140">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c447e-140">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c447e-141">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c447e-141">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
