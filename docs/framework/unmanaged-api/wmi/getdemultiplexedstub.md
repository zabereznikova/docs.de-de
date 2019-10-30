---
title: Getdemultiplexedstub-Funktion (Referenz zur nicht verwalteten API)
description: Die getdemultiplexedstub-Funktion erstellt eine Objekt Weiterleitungs Senke, um einem Client den Empfang von asynchronen Aufrufen von der Windows-Verwaltung zu unterstützen.
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
ms.openlocfilehash: 9cc028b3300b43f8a0fb3e29f8b5ac6e1817b8c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127473"
---
# <a name="getdemultiplexedstub-function"></a>Getdemultiplexedstub-Funktion
Erstellt eine Objektweiterleitungssenke, um einen Client beim Empfang asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>Parameter

`pObject`  
in Ein Zeiger auf die Prozess interne Implementierung von [iwbemubjectsink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)des Clients.

`isLocal`  
in Ein Flag, das angibt, ob das Ereignis lokal (`true`) ist; Andernfalls `false`.

`ppObject`  
vorgenommen Eine-Objekt Weiterleitungs Senke, die einem Client den Empfang von asynchronen Aufrufen von der Windows-Verwaltung unterstützt.

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).

Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null). Um erweiterte Fehlerinformationen abzurufen, wenden Sie die [GetErrorInfo](geterrorinfo.md) -Funktion an.
    
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
