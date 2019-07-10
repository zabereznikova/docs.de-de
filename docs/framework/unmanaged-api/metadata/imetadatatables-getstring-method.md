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
ms.openlocfilehash: 3f817fa3f24bebf3303c656bd02c4d93d1d1431b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781395"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="801d9-102">IMetaDataTables::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="801d9-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="801d9-103">Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte in den Gültigkeitsbereich des aktuellen ab.</span><span class="sxs-lookup"><span data-stu-id="801d9-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="801d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="801d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="801d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="801d9-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="801d9-106">[in] Der Index, an dem beginnen, den nächsten Wert gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="801d9-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="801d9-107">[out] Ein Zeiger auf einen Zeiger auf den Wert der zurückgegebenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="801d9-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="801d9-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="801d9-108">Requirements</span></span>  
 <span data-ttu-id="801d9-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="801d9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="801d9-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="801d9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="801d9-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="801d9-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="801d9-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="801d9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="801d9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="801d9-113">See also</span></span>

- [<span data-ttu-id="801d9-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="801d9-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="801d9-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="801d9-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
