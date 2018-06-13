---
title: GetDemultiplexedStub-Funktion (Referenz zur nicht verwalteten API)
description: Die GetDemultiplexedStub-Funktion erstellt eine Objekt Weiterleitung eine Ereignissenke, bei der ein Client asynchrone Aufrufe von Windows-Verwaltung empfangen.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b195d3a512c537ca409bd2039add9e69abaf4df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456361"
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub-Funktion
Erstellt eine Objekt Weiterleitung eine Ereignissenke, bei der ein Client asynchrone Aufrufe von Windows-Verwaltung empfangen.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>Parameter

`pObject`  
[in] Ein Zeiger auf den Client in-Process-Implementierung von [IWbemObjectSink](https://msdn.microsoft.com/library/aa391787(v=vs.85).aspx).

`isLocal`  
[in] Ein Flag, das angibt, ob das Ereignis lokal ist (`true`) ist, andernfalls `false`.

`ppObject`  
[out] Ein Objekt Weiterleitung Senke eines Clients bei der asynchrone Aufrufe von Windows-Verwaltung empfangen.

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).

Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.
    
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
