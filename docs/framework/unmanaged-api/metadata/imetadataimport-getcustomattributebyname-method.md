---
title: IMetaDataImport::GetCustomAttributeByName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetCustomAttributeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b689c54b5e8d741d32bc941b4e78e6674f15e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="c281e-102">IMetaDataImport::GetCustomAttributeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="c281e-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="c281e-103">Ruft das benutzerdefinierte Attribut mit dem angegebenen Namen und Besitzer ab.</span><span class="sxs-lookup"><span data-stu-id="c281e-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c281e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c281e-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c281e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c281e-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="c281e-106">[in] Ein Metadatentoken, das das Objekt, das das benutzerdefinierte Attribut besitzt darstellt.</span><span class="sxs-lookup"><span data-stu-id="c281e-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="c281e-107">[in] Der Name des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="c281e-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="c281e-108">[out] Ein Zeiger auf ein Array von Daten, die den Wert des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="c281e-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="c281e-109">[out] Die Größe in Bytes der Daten im zurückgegebenen *`ppData`.</span><span class="sxs-lookup"><span data-stu-id="c281e-109">[out] The size in bytes of the data returned in *`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c281e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c281e-110">Remarks</span></span>  
 <span data-ttu-id="c281e-111">Es ist zulässig, mehrere benutzerdefinierte Attribute für den gleichen Besitzer zu definieren; Sie können auch die denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="c281e-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="c281e-112">Allerdings `GetCustomAttributeByName` gibt nur eine Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="c281e-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="c281e-113">(`GetCustomAttributeByName` gibt die erste Instanz, die gefunden wird.) Um alle Instanzen eines benutzerdefinierten Attributs zu suchen, rufen die [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="c281e-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c281e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c281e-114">Requirements</span></span>  
 <span data-ttu-id="c281e-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c281e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c281e-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c281e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c281e-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c281e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c281e-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c281e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c281e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c281e-119">See Also</span></span>  
 [<span data-ttu-id="c281e-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c281e-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c281e-121">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c281e-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
