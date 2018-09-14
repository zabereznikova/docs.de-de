---
title: GetDemultiplexedStub-Funktion (Referenz zur nicht verwalteten API)
description: Die GetDemultiplexedStub-Funktion erstellt, eine Objektsenke für die Weiterleitung, bei der ein Client asynchrone Aufrufe aus der Windows-Verwaltung empfangen wird.
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
ms.openlocfilehash: 4311a77c9159428bf7beacc99d4479acb28b91b6
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45529661"
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub-Funktion
Erstellt eine Objektweiterleitungssenke, um einen Client beim Empfang asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.
  
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
[in] Ein Zeiger auf dem Client in-Process-Implementierung von [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).

`isLocal`  
[in] Ein Flag, das angibt, ob das Ereignis lokal ist (`true`) ist, andernfalls `false`.

`ppObject`  
[out] Eine Weiterleitung Objektsenke bei einem Client beim Empfang von asynchroner Aufrufen von der Windows-Verwaltung.

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist `S_OK` (0).

Wenn die Funktion fehlschlägt, ist der Rückgabewert ein NULL-Fehlercode. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.
    
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
