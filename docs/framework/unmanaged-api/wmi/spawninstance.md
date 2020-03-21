---
title: SpawnInstance-Funktion (Nicht verwaltete API-Referenz)
description: Die SpawnInstance-Funktion erstellt eine neue Instanz einer Klasse.
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
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176720"
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
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in]: Reserviert Dieser Parameter muss 0 sein.

`ppNewInstance`  
[out] Empfängt den Zeiger auf die neue Instanz der Klasse. Wenn ein Fehler auftritt, wird ein `ppNewInstance` neues Objekt nicht zurückgegeben und unverändert gelassen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr`ist keine gültige Klassendefinition und kann keine neuen Instanzen erstellen. Entweder ist es unvollständig oder es wurde nicht bei der Windows-Verwaltung registriert, indem [PutClassWmi](putclasswmi.md)aufgerufen wurde. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` ist `null` |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::SpawnInstance-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)

`ptr`muss eine Klassendefinition sein, die von der Windows-Verwaltung abgerufen wurde. (Beachten Sie, dass das Erstellen einer Instanz von einer Instanz unterstützt wird, die zurückgegebene Instanz jedoch leer ist.) Anschließend verwenden Sie diese Klassendefinition, um neue Instanzen zu erstellen. Wenn Sie die Instanz in die Windows-Verwaltung schreiben möchten, ist ein Aufruf der [PutInstanceWmi-Funktion](putinstancewmi.md) erforderlich.

Das neue Objekt, das zurückgegeben wird, `ppNewClass` wird automatisch zu einer Unterklasse des aktuellen Objekts. Dieses Verhalten kann nicht überschrieben werden. Es gibt keine andere Methode, mit der Unterklassen (abgeleitete Klassen) erstellt werden können.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
