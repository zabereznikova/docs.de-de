---
title: SpawnInstance-Funktion (Referenz zur nicht verwalteten API)
description: Die SpawnInstance-Funktion erstellt eine neue Instanz einer-Klasse.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f93b4fbd5429ed2bdae8fb707e61df024cd8fd6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107513"
---
# <a name="spawninstance-function"></a>SpawnInstance-Funktion
Erstellt eine neue Instanz einer Klasse.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`lFlags`  
[in]: Reserviert Dieser Parameter muss 0 sein.

`ppNewInstance`  
vorgenommen Empfängt den Zeiger auf die neue Instanz der-Klasse. Wenn ein Fehler auftritt, wird kein neues Objekt zurückgegeben, und `ppNewInstance` bleibt unverändert.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr` ist keine gültige Klassendefinition und kann keine neuen Instanzen erzeugen. Sie ist entweder unvollständig oder wurde nicht bei der Windows-Verwaltung durch Aufrufen von [putclasswmi](putclasswmi.md)registriert. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` ist `null`. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) -Methode.

`ptr` muss eine Klassendefinition sein, die aus der Windows-Verwaltung abgerufen wird. (Beachten Sie, dass das Erzeugen einer Instanz aus einer-Instanz unterstützt wird, aber die zurückgegebene-Instanz leer ist.) Anschließend verwenden Sie diese Klassendefinition, um neue Instanzen zu erstellen. Wenn Sie beabsichtigen, die Instanz in die Windows-Verwaltung zu schreiben, ist ein Rückruf der [putinstancewmi](putinstancewmi.md) -Funktion erforderlich.

Das neue-Objekt, das in `ppNewClass` zurückgegeben wird, wird automatisch zu einer Unterklasse des aktuellen-Objekts. Dieses Verhalten kann nicht überschrieben werden. Es gibt keine andere Methode, mit der Unterklassen (abgeleitete Klassen) erstellt werden können.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
