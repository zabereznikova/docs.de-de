---
title: SpawnDerivedClass-Funktion (Referenz zur nicht verwalteten API)
description: Die SpawnDerivedClass-Funktion erstellt ein neues Objekt, das von einem Objekt abgeleitet ist.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04df65a29584f7e2de44389d815b915a541e38f0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507496"
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass-Funktion
Erstellt ein neu abgeleitetes Klassenobjekt aus einem angegebenen Objekt.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`ppNewClass`  
[out] Erhält der Zeiger auf das neue Objekt der Klasse-Definition. Wenn ein Fehler auftritt, ist ein neues Objekt nicht zurückgegeben, und `ppNewClass` wird links unverändert. Der Wert darf nicht sein `null`.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Es wurde ein allgemeiner Fehler. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Es wurde eine ungültige Operation, z. B. das Erzeugen einer Klasse von einer Instanz angefordert. |
| `WBEM_E_INCOMPLETE_CLASS` | Die Quellklasse wurde nicht vollständig definiert oder mit Windows-Verwaltung, registriert werden, damit eine neue abgeleitete Klasse nicht zulässig ist. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | `ppNewClass` ist `null`. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) Methode.

`ptr` muss eine Definition einer Klasse, die die übergeordnete Klasse des Objekts erzeugten wird. Das zurückgegebene Objekt ist eine Unterklasse des aktuellen Objekts.

Das neue Objekt im zurückgegebenen `ppNewClass` wird automatisch eine Unterklasse des aktuellen Objekts. Dieses Verhalten kann nicht überschrieben werden. Es gibt keine andere Methode, die von der Unterklasse (abgeleitete Klassen) erstellt werden können.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
