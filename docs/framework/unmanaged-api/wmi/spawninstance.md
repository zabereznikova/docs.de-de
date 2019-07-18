---
title: SpawnInstance-Funktion (Referenz zur nicht verwalteten API)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97a3ab62cda82526a7ad8b8e5d985d9fce7d6f07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783069"
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
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`ppNewInstance`  
[out] Erhält der Zeiger auf die neue Instanz der Klasse. Wenn ein Fehler auftritt, ist ein neues Objekt nicht zurückgegeben, und `ppNewInstance` wird links unverändert.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr` ist keine gültige Klassendefinition und können keine neue Instanzen erzeugen. Entweder ist es unvollständig, oder es wurde nicht registriert mit der Windows-Verwaltung durch den Aufruf [PutClassWmi](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` ist `null`. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) Methode.

`ptr` eine Definition einer Klasse muss aus der Verwaltung von Windows abgerufen werden. (Beachten Sie, dass erzeugen eine Instanz von einer Instanz unterstützt wird, aber die zurückgegebene Instanz ist leer.) Anschließend verwenden Sie diese Klassendefinition, um die neue Instanzen zu erstellen. Ein Aufruf der [PutInstanceWmi](putinstancewmi.md) Funktion ist erforderlich, wenn Sie beabsichtigen, die Instanz für die Verwaltung von Windows zu schreiben.

Das neue Objekt im zurückgegebenen `ppNewClass` wird automatisch eine Unterklasse des aktuellen Objekts. Dieses Verhalten kann nicht überschrieben werden. Es gibt keine andere Methode, die von der Unterklasse (abgeleitete Klassen) erstellt werden können.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
