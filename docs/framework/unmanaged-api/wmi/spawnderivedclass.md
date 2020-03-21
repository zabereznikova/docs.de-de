---
title: SpawnDerivedClass-Funktion (nicht verwaltete API-Referenz)
description: Die Funktion SpawnDerivedClass erstellt ein neues Objekt, das von einem Objekt abgeleitet wird.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174848"
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass-Funktion
Erstellt ein neu abgeleitetes Klassenobjekt aus einem angegebenen Objekt.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in]: Reserviert Dieser Parameter muss 0 sein.

`ppNewClass`  
[out] Empfängt den Zeiger auf das neue Klassendefinitionsobjekt. Wenn ein Fehler auftritt, wird ein `ppNewClass` neues Objekt nicht zurückgegeben und unverändert gelassen. Sein Wert `null`kann nicht sein.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeines Versagen aufgetreten. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Ein ungültiger Vorgang, z. B. das Erstellen einer Klasse aus einer Instanz, wurde angefordert. |
| `WBEM_E_INCOMPLETE_CLASS` | Die Quellklasse war nicht vollständig bei windows Management definiert oder registriert, daher ist eine neue abgeleitete Klasse nicht zulässig. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` ist `null` |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::SpawnDerivedClass-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)

`ptr`muss eine Klassendefinition sein, die zur übergeordneten Klasse des erstellten Objekts wird. Das zurückgegebene Objekt wird zu einer Unterklasse des aktuellen Objekts.

Das neue Objekt, das zurückgegeben wird, `ppNewClass` wird automatisch zu einer Unterklasse des aktuellen Objekts. Dieses Verhalten kann nicht überschrieben werden. Es gibt keine andere Methode, mit der Unterklassen (abgeleitete Klassen) erstellt werden können.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
