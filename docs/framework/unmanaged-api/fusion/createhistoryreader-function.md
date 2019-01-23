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
ms.openlocfilehash: 8beb5e64b05f50ba61ced72fcdb7700d4b9f30e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505041"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="492cd-102">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="492cd-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="492cd-103">Erstellt einen Verlauf Leser für die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="492cd-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="492cd-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="492cd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="492cd-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="492cd-106">[in] Der Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="492cd-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="492cd-107">[out] Bei erfolgreichem Abschluss können Sie einen Zeiger auf den Verlaufsreader enthält.</span><span class="sxs-lookup"><span data-stu-id="492cd-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="492cd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="492cd-108">Return Value</span></span>  
 <span data-ttu-id="492cd-109">Diese Methode gibt die standard-COM-Fehlercodes zurück, wie definiert in "Winerror.h", zusätzlich zu den Werten in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="492cd-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="492cd-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="492cd-110">Return code</span></span>|<span data-ttu-id="492cd-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="492cd-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="492cd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="492cd-112">S_OK</span></span>|<span data-ttu-id="492cd-113">Gibt an, dass die Methode erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="492cd-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="492cd-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="492cd-114">E_INVALIDARG</span></span>|<span data-ttu-id="492cd-115">Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf einen null-Verweis festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="492cd-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="492cd-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="492cd-116">Requirements</span></span>  
 <span data-ttu-id="492cd-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="492cd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="492cd-118">**Bibliothek:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="492cd-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="492cd-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="492cd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492cd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="492cd-120">See also</span></span>
- [<span data-ttu-id="492cd-121">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="492cd-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
