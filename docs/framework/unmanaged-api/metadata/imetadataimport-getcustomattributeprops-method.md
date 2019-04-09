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
ms.openlocfilehash: c27a55166ebc055f324ec45ba6dfd835c8b8bbf6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075742"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="37670-102">IMetaDataImport::GetCustomAttributeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="37670-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="37670-103">Ruft den Wert des benutzerdefinierten Attributs ab, wenn sein Metadatentoken angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="37670-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37670-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37670-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37670-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37670-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="37670-106">[in] Ein Metadatentoken, das das benutzerdefinierte Attribut darstellt, das abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="37670-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="37670-107">[out, optional] Ein Metadatentoken, das das Objekt darstellt, das das benutzerdefinierte Attribut ändert.</span><span class="sxs-lookup"><span data-stu-id="37670-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="37670-108">Dieser Wert kann jeder Typ von Metadatentoken außer `mdCustomAttribute` sein.</span><span class="sxs-lookup"><span data-stu-id="37670-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="37670-109">[out, optional] Ein `mdMethodDef`- oder ein `mdMemberRef`-Metadatentoken, das den <xref:System.Type> des zurückgegebenen benutzerdefinierten Attributs darstellt.</span><span class="sxs-lookup"><span data-stu-id="37670-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="37670-110">[out, optional] Ein Zeiger auf ein Datenarray, das der Wert des benutzerdefinierten Attributs ist.</span><span class="sxs-lookup"><span data-stu-id="37670-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="37670-111">[out, optional] Die Größe der in \*`ppBlob` zurückgegebenen Daten in Bytes .</span><span class="sxs-lookup"><span data-stu-id="37670-111">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37670-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="37670-112">Remarks</span></span>  
 <span data-ttu-id="37670-113">Ein benutzerdefiniertes Attribut wird als ein Datenarray gespeichert. Dies ist das Format, das von der Metadaten-Engine erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="37670-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37670-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37670-114">Requirements</span></span>  
 <span data-ttu-id="37670-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37670-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37670-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37670-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37670-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="37670-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="37670-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="37670-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37670-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37670-119">See also</span></span>

- [<span data-ttu-id="37670-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37670-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="37670-121">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37670-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
