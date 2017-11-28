---
title: Initialize-Funktion (Referenz zur nicht verwalteten API)
description: "Die Initialize-Funktion führt eine WMI-Initialisierung."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Initialize
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Initialize
helpviewer_keywords: Initialize function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ed0e0127608f9f80a2661067dd9a6025fd579a7
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="initialize-function"></a>Initialize-Funktion
Führt eine WMI-Initialisierung.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a>Parameter

`bAllowIManagementObjectQI`   
[in] `true` , um anzugeben, dass Aufrufe von QueryInterface auf WMI-Objekte zulässig sind; `false` andernfalls.

## <a name="return-value"></a>Rückgabewert

Die Funktion gibt immer zurück `S_OK` (0).
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.def  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
