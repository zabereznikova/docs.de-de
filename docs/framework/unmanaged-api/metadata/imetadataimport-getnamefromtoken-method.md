---
title: IMetaDataImport::GetNameFromToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNameFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e77954d5730417a005c6c1ac07fa171bd0f1b13a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="1758a-102">IMetaDataImport::GetNameFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="1758a-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="1758a-103">Ruft den UTF-8-Namen des Objekts ab, auf das vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1758a-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="1758a-104">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="1758a-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1758a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1758a-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1758a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1758a-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="1758a-107">[in] Das Token, die zum Zurückgeben des Namens für das Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="1758a-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="1758a-108">[out] Ein Zeiger auf den UTF-8-Objektnamen im Heap.</span><span class="sxs-lookup"><span data-stu-id="1758a-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1758a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1758a-109">Remarks</span></span>  
 <span data-ttu-id="1758a-110">`GetNameFromToken` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="1758a-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="1758a-111">Als Alternative, rufen Sie eine Methode zum Abrufen der Eigenschaften von den betreffenden Typ des Tokens, die erforderlich sind, z. B. `GetFieldProps` für ein Feld oder `GetMethodProps` für eine Methode.</span><span class="sxs-lookup"><span data-stu-id="1758a-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1758a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1758a-112">Requirements</span></span>  
 <span data-ttu-id="1758a-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1758a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1758a-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1758a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1758a-115">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1758a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1758a-116">**.NET Framework-Versionen:** 1.0</span><span class="sxs-lookup"><span data-stu-id="1758a-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1758a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1758a-117">See Also</span></span>  
 [<span data-ttu-id="1758a-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1758a-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1758a-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1758a-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
