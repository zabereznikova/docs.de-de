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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb26a96c46b01a2981afba0ac6b405c0b50f6d9a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781419"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="c7d9e-102">IMetaDataTables::GetNumTables-Methode</span><span class="sxs-lookup"><span data-stu-id="c7d9e-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="c7d9e-103">Ruft die Anzahl der Tabellen im Bereich des aktuellen `IMetaDataTables` Instanz.</span><span class="sxs-lookup"><span data-stu-id="c7d9e-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7d9e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7d9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7d9e-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="c7d9e-106">[out] Ein Zeiger auf die Anzahl der Tabellen im Gültigkeitsbereich der aktuellen Instanz.</span><span class="sxs-lookup"><span data-stu-id="c7d9e-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7d9e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7d9e-107">Requirements</span></span>  
 <span data-ttu-id="c7d9e-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7d9e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d9e-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c7d9e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7d9e-110">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c7d9e-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7d9e-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7d9e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d9e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7d9e-112">See also</span></span>

- [<span data-ttu-id="c7d9e-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7d9e-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c7d9e-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7d9e-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
