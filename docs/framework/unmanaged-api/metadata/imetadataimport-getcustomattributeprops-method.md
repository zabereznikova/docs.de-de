---
title: IMetaDataImport::GetCustomAttributeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c714915651d8660a739d8ee6518fc3814af4c08d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782416"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="89a8e-102">IMetaDataImport::GetCustomAttributeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="89a8e-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="89a8e-103">Ruft den Wert des benutzerdefinierten Attributs ab, wenn sein Metadatentoken angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="89a8e-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a8e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89a8e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89a8e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89a8e-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="89a8e-106">[in] Ein Metadatentoken, das das benutzerdefinierte Attribut darstellt, das abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="89a8e-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="89a8e-107">[out, optional] Ein Metadatentoken, das das Objekt darstellt, das das benutzerdefinierte Attribut ändert.</span><span class="sxs-lookup"><span data-stu-id="89a8e-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="89a8e-108">Dieser Wert kann jeder Typ von Metadatentoken außer `mdCustomAttribute` sein.</span><span class="sxs-lookup"><span data-stu-id="89a8e-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="89a8e-109">[out, optional] Ein `mdMethodDef`- oder ein `mdMemberRef`-Metadatentoken, das den <xref:System.Type> des zurückgegebenen benutzerdefinierten Attributs darstellt.</span><span class="sxs-lookup"><span data-stu-id="89a8e-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="89a8e-110">[out, optional] Ein Zeiger auf ein Datenarray, das der Wert des benutzerdefinierten Attributs ist.</span><span class="sxs-lookup"><span data-stu-id="89a8e-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="89a8e-111">[out, optional] Die Größe der in \*`ppBlob` zurückgegebenen Daten in Bytes .</span><span class="sxs-lookup"><span data-stu-id="89a8e-111">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89a8e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89a8e-112">Remarks</span></span>  
 <span data-ttu-id="89a8e-113">Ein benutzerdefiniertes Attribut wird als ein Datenarray gespeichert. Dies ist das Format, das von der Metadaten-Engine erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="89a8e-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a8e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89a8e-114">Requirements</span></span>  
 <span data-ttu-id="89a8e-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a8e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a8e-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89a8e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89a8e-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="89a8e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89a8e-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a8e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a8e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89a8e-119">See also</span></span>

- [<span data-ttu-id="89a8e-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a8e-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="89a8e-121">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a8e-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
