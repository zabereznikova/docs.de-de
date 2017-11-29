---
title: VerifyClientKey-Funktion (Referenz zur nicht verwalteten API)
description: "Die VerifyClientKey-Funktion wird sichergestellt, dass der Clientschlüssel die richtigen Sicherheit besitzt."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: VerifyClientKey
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: VerifyClientKey
helpviewer_keywords: VerifyClientKey function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cce10e3dd5536a85b4dee62cc7f6e9e8e73929cb
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="bf586-103">VerifyClientKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="bf586-103">VerifyClientKey function</span></span>
<span data-ttu-id="bf586-104">Stellt sicher, dass der Clientschlüssel die richtigen Sicherheit verfügt.</span><span class="sxs-lookup"><span data-stu-id="bf586-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bf586-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf586-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="bf586-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bf586-106">Return value</span></span>

<span data-ttu-id="bf586-107">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="bf586-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="bf586-108">Wenn die Funktion fehlschlägt, wird der Rückgabewert ist ein NULL-Fehlercode, der definiert *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="bf586-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf586-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf586-109">Requirements</span></span>  
 <span data-ttu-id="bf586-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf586-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf586-111">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="bf586-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="bf586-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf586-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf586-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf586-113">See also</span></span>  
[<span data-ttu-id="bf586-114">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="bf586-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
