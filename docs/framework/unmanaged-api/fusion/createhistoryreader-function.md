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
ms.openlocfilehash: 2710d14d6e73879fd17a6b58659463ea205f2384
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795364"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="2427a-102">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="2427a-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="2427a-103">Erstellt einen Verlaufs Leser für die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="2427a-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2427a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2427a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2427a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2427a-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="2427a-106">in Der Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="2427a-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="2427a-107">vorgenommen Nach erfolgreichem Abschluss enthält einen Zeiger auf den Verlaufs Leser.</span><span class="sxs-lookup"><span data-stu-id="2427a-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2427a-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2427a-108">Return Value</span></span>  
 <span data-ttu-id="2427a-109">Diese Methode gibt zusätzlich zu den in der folgenden Tabelle beschriebenen Werten com-Standard Fehlercodes zurück, die in WinError. h definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2427a-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="2427a-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="2427a-110">Return code</span></span>|<span data-ttu-id="2427a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2427a-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2427a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2427a-112">S_OK</span></span>|<span data-ttu-id="2427a-113">Gibt an, dass die Methode erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2427a-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="2427a-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2427a-114">E_INVALIDARG</span></span>|<span data-ttu-id="2427a-115">Gibt an `wzFilePath` , `ppHistoryReader` dass oder auf einen NULL-Verweis festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2427a-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2427a-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2427a-116">Requirements</span></span>  
 <span data-ttu-id="2427a-117">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2427a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2427a-118">**Fern** Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="2427a-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="2427a-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2427a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2427a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2427a-120">See also</span></span>

- [<span data-ttu-id="2427a-121">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="2427a-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
