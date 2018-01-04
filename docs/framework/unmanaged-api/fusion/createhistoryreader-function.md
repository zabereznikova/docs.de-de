---
title: CreateHistoryReader-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab5e54735c360cb7bd2e681c04b0b1ae491bd716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="ba442-102">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="ba442-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="ba442-103">Erstellt einen Leser Verlauf für die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="ba442-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba442-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba442-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba442-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba442-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="ba442-106">[in] Der Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="ba442-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="ba442-107">[out] Bei erfolgreichem Abschluss können Sie einen Zeiger auf den Verlaufsreader enthält.</span><span class="sxs-lookup"><span data-stu-id="ba442-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba442-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ba442-108">Return Value</span></span>  
 <span data-ttu-id="ba442-109">Diese Methode gibt COM-Standardfehlercodes in WinError.h definiert, zusätzlich zu den Werten in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba442-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="ba442-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="ba442-110">Return code</span></span>|<span data-ttu-id="ba442-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba442-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ba442-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba442-112">S_OK</span></span>|<span data-ttu-id="ba442-113">Gibt an, dass die Methode erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba442-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="ba442-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ba442-114">E_INVALIDARG</span></span>|<span data-ttu-id="ba442-115">Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf ein null-Verweis festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ba442-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba442-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba442-116">Requirements</span></span>  
 <span data-ttu-id="ba442-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba442-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba442-118">**Bibliothek:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="ba442-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="ba442-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba442-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba442-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba442-120">See Also</span></span>  
 [<span data-ttu-id="ba442-121">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="ba442-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
