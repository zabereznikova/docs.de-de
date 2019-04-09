---
title: IMetaDataImport::GetCustomAttributeByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61029074347d554faaefe790c1e408e860e34690
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183026"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="9e5c6-102">IMetaDataImport::GetCustomAttributeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="9e5c6-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="9e5c6-103">Ruft das benutzerdefinierte Attribut, mit dem angegebenen Namen und Besitzer ab.</span><span class="sxs-lookup"><span data-stu-id="9e5c6-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e5c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e5c6-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e5c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e5c6-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="9e5c6-106">[in] Ein Metadatentoken, das das Objekt, das Besitzer des benutzerdefinierten Attributs darstellt.</span><span class="sxs-lookup"><span data-stu-id="9e5c6-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="9e5c6-107">[in] Der Name des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="9e5c6-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="9e5c6-108">[out] Ein Zeiger auf ein Array von Daten, die den Wert des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="9e5c6-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="9e5c6-109">[out] Die Größe in Bytes der Daten im zurückgegebenen \*`ppData`.</span><span class="sxs-lookup"><span data-stu-id="9e5c6-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e5c6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e5c6-110">Remarks</span></span>  
 <span data-ttu-id="9e5c6-111">Es ist zulässig, mehrere benutzerdefinierte Attribute für den gleichen Besitzer zu definieren; Sie können auch den gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="9e5c6-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="9e5c6-112">Allerdings `GetCustomAttributeByName` gibt nur eine Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="9e5c6-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="9e5c6-113">(`GetCustomAttributeByName` gibt die erste Instanz, die es auftritt.) Um alle Instanzen eines benutzerdefinierten Attributs zu suchen, rufen die [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9e5c6-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e5c6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e5c6-114">Requirements</span></span>  
 <span data-ttu-id="9e5c6-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e5c6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e5c6-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9e5c6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e5c6-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9e5c6-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="9e5c6-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="9e5c6-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9e5c6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e5c6-119">See also</span></span>

- [<span data-ttu-id="9e5c6-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e5c6-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9e5c6-121">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e5c6-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
