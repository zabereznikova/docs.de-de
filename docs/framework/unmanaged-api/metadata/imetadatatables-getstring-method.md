---
title: IMetaDataTables::GetString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fed98521c0609ebd8b5f65885d69c77814e9e85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119339"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="4821d-102">IMetaDataTables::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="4821d-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="4821d-103">Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte in den Gültigkeitsbereich des aktuellen ab.</span><span class="sxs-lookup"><span data-stu-id="4821d-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4821d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4821d-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4821d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4821d-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="4821d-106">[in] Der Index, an dem beginnen, den nächsten Wert gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="4821d-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="4821d-107">[out] Ein Zeiger auf einen Zeiger auf den Wert der zurückgegebenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4821d-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4821d-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4821d-108">Requirements</span></span>  
 <span data-ttu-id="4821d-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4821d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4821d-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4821d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4821d-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4821d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="4821d-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4821d-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4821d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4821d-113">See also</span></span>

- [<span data-ttu-id="4821d-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4821d-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="4821d-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4821d-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
