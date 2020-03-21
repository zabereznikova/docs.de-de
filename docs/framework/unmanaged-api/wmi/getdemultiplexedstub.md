---
title: GetDemultiplexedStub-Funktion (Nicht verwaltete API-Referenz)
description: Die GetDemultiplexedStub-Funktion erstellt eine Objektweiterleitungssensenke, um einen Client beim Empfangen asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.
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
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174965"
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub-Funktion
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
[in] Ein Zeiger auf die prozessübergreifende Implementierung von [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).

`isLocal`  
[in] Ein Flag, das angibt,`true`ob das Ereignis lokal ist ( ); andernfalls `false`.

`ppObject`  
[out] Eine Objektweiterleitungssenke, um einen Client beim Empfangen asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, `S_OK` ist der Rückgabewert (0).

Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null. Um erweiterte Fehlerinformationen zu erhalten, rufen Sie die [GetErrorInfo-Funktion](geterrorinfo.md) auf.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
