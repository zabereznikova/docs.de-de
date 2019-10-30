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
ms.openlocfilehash: 80979f0424469bb1d4771ad6507bb8c9d5364ab4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108611"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="1c5f4-102">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="1c5f4-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="1c5f4-103">Erstellt einen Verlaufs Leser für die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="1c5f4-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c5f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c5f4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c5f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c5f4-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="1c5f4-106">in Der Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="1c5f4-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="1c5f4-107">vorgenommen Nach erfolgreichem Abschluss enthält einen Zeiger auf den Verlaufs Leser.</span><span class="sxs-lookup"><span data-stu-id="1c5f4-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c5f4-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1c5f4-108">Return Value</span></span>  
 <span data-ttu-id="1c5f4-109">Diese Methode gibt zusätzlich zu den in der folgenden Tabelle beschriebenen Werten com-Standard Fehlercodes zurück, die in WinError. h definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1c5f4-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="1c5f4-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="1c5f4-110">Return code</span></span>|<span data-ttu-id="1c5f4-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c5f4-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1c5f4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c5f4-112">S_OK</span></span>|<span data-ttu-id="1c5f4-113">Gibt an, dass die Methode erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1c5f4-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="1c5f4-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1c5f4-114">E_INVALIDARG</span></span>|<span data-ttu-id="1c5f4-115">Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf einen NULL-Verweis festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="1c5f4-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c5f4-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c5f4-116">Requirements</span></span>  
 <span data-ttu-id="1c5f4-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c5f4-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c5f4-118">**Bibliothek:** Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="1c5f4-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="1c5f4-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c5f4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5f4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c5f4-120">See also</span></span>

- [<span data-ttu-id="1c5f4-121">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="1c5f4-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
