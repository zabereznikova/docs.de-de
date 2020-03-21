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
ms.openlocfilehash: 216a1f7bd2ff5a596fa7abf7874b5e603d5a9f7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175238"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="65b52-102">IMetaDataTables::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="65b52-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="65b52-103">Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte im aktuellen Referenzbereich ab.</span><span class="sxs-lookup"><span data-stu-id="65b52-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65b52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65b52-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65b52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65b52-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="65b52-106">[in] Der Index, an dem nach dem nächsten Wert gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="65b52-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="65b52-107">[out] Ein Zeiger auf einen Zeiger auf den zurückgegebenen Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="65b52-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b52-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="65b52-108">Requirements</span></span>  
 <span data-ttu-id="65b52-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65b52-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65b52-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="65b52-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65b52-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="65b52-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="65b52-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65b52-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b52-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65b52-113">See also</span></span>

- [<span data-ttu-id="65b52-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65b52-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="65b52-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65b52-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
