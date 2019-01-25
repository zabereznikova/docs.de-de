---
title: IMetaDataTables::GetUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52f3f382e022600e946a4c8f531f4eea5f3d8a34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693742"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="306f6-102">IMetaDataTables::GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="306f6-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="306f6-103">Ruft die hartcodierten Zeichenfolge am angegebenen Index in die Zeichenfolgenspalte im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="306f6-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="306f6-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="306f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="306f6-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="306f6-106">[in] Der Indexwert aus dem die hartcodierten Zeichenfolge abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="306f6-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="306f6-107">[out] P, Zeiger auf die Größe von `ppData`.</span><span class="sxs-lookup"><span data-stu-id="306f6-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="306f6-108">[out] Ein Zeiger auf einen Zeiger auf die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="306f6-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306f6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="306f6-109">Requirements</span></span>  
 <span data-ttu-id="306f6-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306f6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306f6-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="306f6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="306f6-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="306f6-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="306f6-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306f6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="306f6-114">See also</span></span>
- [<span data-ttu-id="306f6-115">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="306f6-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="306f6-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="306f6-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
