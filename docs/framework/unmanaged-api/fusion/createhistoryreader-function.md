---
title: CreateHistoryReader-Funktion
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e438006d6424866514e73119c05e8fd69d7ba62e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132261"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="ff5d4-102">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="ff5d4-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="ff5d4-103">Erstellt einen Verlauf Leser für die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="ff5d4-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff5d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff5d4-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff5d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff5d4-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="ff5d4-106">[in] Der Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="ff5d4-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="ff5d4-107">[out] Bei erfolgreichem Abschluss können Sie einen Zeiger auf den Verlaufsreader enthält.</span><span class="sxs-lookup"><span data-stu-id="ff5d4-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff5d4-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ff5d4-108">Return Value</span></span>  
 <span data-ttu-id="ff5d4-109">Diese Methode gibt die standard-COM-Fehlercodes zurück, wie definiert in "Winerror.h", zusätzlich zu den Werten in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff5d4-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="ff5d4-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="ff5d4-110">Return code</span></span>|<span data-ttu-id="ff5d4-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff5d4-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ff5d4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff5d4-112">S_OK</span></span>|<span data-ttu-id="ff5d4-113">Gibt an, dass die Methode erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ff5d4-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="ff5d4-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ff5d4-114">E_INVALIDARG</span></span>|<span data-ttu-id="ff5d4-115">Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf einen null-Verweis festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ff5d4-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff5d4-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff5d4-116">Requirements</span></span>  
 <span data-ttu-id="ff5d4-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff5d4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff5d4-118">**Bibliothek:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="ff5d4-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="ff5d4-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff5d4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff5d4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff5d4-120">See also</span></span>

- [<span data-ttu-id="ff5d4-121">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="ff5d4-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
