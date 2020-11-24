---
title: IMetaDataTables::GetNumTables-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
ms.openlocfilehash: 7e1ea16e7954f21b1349e88d43d7e3b271a57ed7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680291"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="677ec-102">IMetaDataTables::GetNumTables-Methode</span><span class="sxs-lookup"><span data-stu-id="677ec-102">IMetaDataTables::GetNumTables Method</span></span>

<span data-ttu-id="677ec-103">Ruft die Anzahl der Tabellen im Gültigkeitsbereich der aktuellen `IMetaDataTables` Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="677ec-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="677ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="677ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="677ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="677ec-105">Parameters</span></span>  

 `pcTables`  
 <span data-ttu-id="677ec-106">vorgenommen Ein Zeiger auf die Anzahl der Tabellen im aktuellen Instanzbereich.</span><span class="sxs-lookup"><span data-stu-id="677ec-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="677ec-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="677ec-107">Requirements</span></span>  

 <span data-ttu-id="677ec-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="677ec-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="677ec-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="677ec-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="677ec-110">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="677ec-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="677ec-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="677ec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="677ec-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="677ec-112">See also</span></span>

- [<span data-ttu-id="677ec-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="677ec-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="677ec-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="677ec-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
