---
title: IMetaDataImport::GetMethodProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 3c7c3525f2f8753241c9a206e4cf5e552bf06efe
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503626"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="7fd08-102">IMetaDataImport::GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="7fd08-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="7fd08-103">Ruft die Metadaten ab, die der Methode zugeordnet sind, auf die durch das angegebene MethodDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7fd08-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fd08-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fd08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7fd08-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="7fd08-106">in Das MethodDef-Token, das die Methode darstellt, für die Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7fd08-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="7fd08-107">vorgenommen Ein Zeiger auf ein TypeDef-Token, das den Typ darstellt, der die Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="7fd08-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="7fd08-108">vorgenommen Ein Zeiger auf einen Puffer, der den Methodennamen aufweist.</span><span class="sxs-lookup"><span data-stu-id="7fd08-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="7fd08-109">in Die angeforderte Größe von `szMethod` .</span><span class="sxs-lookup"><span data-stu-id="7fd08-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="7fd08-110">vorgenommen Ein Zeiger auf die Größe in breit Zeichen von `szMethod` oder im Fall von abschneiden die tatsächliche Anzahl von breit Zeichen im Methodennamen.</span><span class="sxs-lookup"><span data-stu-id="7fd08-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="7fd08-111">vorgenommen Ein Zeiger auf alle Flags, die der Methode zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="7fd08-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="7fd08-112">vorgenommen Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="7fd08-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="7fd08-113">vorgenommen Ein Zeiger auf die Größe in Byte `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="7fd08-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="7fd08-114">vorgenommen Ein Zeiger auf die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="7fd08-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="7fd08-115">vorgenommen Ein Zeiger auf alle Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="7fd08-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fd08-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7fd08-116">Requirements</span></span>  
 <span data-ttu-id="7fd08-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fd08-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fd08-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7fd08-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fd08-119">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7fd08-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7fd08-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fd08-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd08-121">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7fd08-121">See also</span></span>

- [<span data-ttu-id="7fd08-122">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fd08-122">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7fd08-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fd08-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
