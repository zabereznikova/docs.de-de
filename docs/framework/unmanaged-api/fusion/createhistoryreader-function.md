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
ms.openlocfilehash: 9dae3f1403d33aaf3cfb87d17856640548a90b4d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688940"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="6dd21-102">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="6dd21-102">CreateHistoryReader Function</span></span>

<span data-ttu-id="6dd21-103">Erstellt einen Verlaufs Leser für die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="6dd21-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dd21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dd21-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dd21-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6dd21-105">Parameters</span></span>  

 `wzFilePath`  
 <span data-ttu-id="6dd21-106">in Der Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="6dd21-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="6dd21-107">vorgenommen Nach erfolgreichem Abschluss enthält einen Zeiger auf den Verlaufs Leser.</span><span class="sxs-lookup"><span data-stu-id="6dd21-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dd21-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6dd21-108">Return Value</span></span>  

 <span data-ttu-id="6dd21-109">Diese Methode gibt zusätzlich zu den in der folgenden Tabelle beschriebenen Werten com-Standard Fehlercodes zurück, die in WinError. h definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6dd21-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="6dd21-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="6dd21-110">Return code</span></span>|<span data-ttu-id="6dd21-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6dd21-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6dd21-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dd21-112">S_OK</span></span>|<span data-ttu-id="6dd21-113">Gibt an, dass die Methode erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="6dd21-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="6dd21-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6dd21-114">E_INVALIDARG</span></span>|<span data-ttu-id="6dd21-115">Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf einen NULL-Verweis festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6dd21-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6dd21-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6dd21-116">Requirements</span></span>  

 <span data-ttu-id="6dd21-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dd21-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dd21-118">**Bibliothek:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="6dd21-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="6dd21-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dd21-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd21-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6dd21-120">See also</span></span>

- [<span data-ttu-id="6dd21-121">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="6dd21-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
