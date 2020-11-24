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
ms.openlocfilehash: 8ecaa003084064be1071a85aa726c38d773ec0b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672577"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="fcaf1-102">IMetaDataTables::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="fcaf1-102">IMetaDataTables::GetString Method</span></span>

<span data-ttu-id="fcaf1-103">Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte im aktuellen Verweis Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="fcaf1-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcaf1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcaf1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcaf1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fcaf1-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="fcaf1-106">in Der Index, an dem mit der Suche nach dem nächsten Wert begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="fcaf1-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="fcaf1-107">vorgenommen Ein Zeiger auf einen Zeiger auf den zurückgegebenen Zeichen folgen Wert.</span><span class="sxs-lookup"><span data-stu-id="fcaf1-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcaf1-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fcaf1-108">Requirements</span></span>  

 <span data-ttu-id="fcaf1-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcaf1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcaf1-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fcaf1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fcaf1-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcaf1-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fcaf1-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcaf1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcaf1-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcaf1-113">See also</span></span>

- [<span data-ttu-id="fcaf1-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcaf1-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="fcaf1-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcaf1-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
