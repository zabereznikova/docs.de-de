---
title: SpawnDerivedClass-Funktion (Referenz zur nicht verwalteten API)
description: Die SpawnDerivedClass-Funktion erstellt ein neues Objekt, das von einem Objekt abgeleitet wird.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnDerivedClass
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnDerivedClass
helpviewer_keywords: SpawnDerivedClass function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16f9a762c87e1e181202739b70cd978a80864f04
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass-Funktion
Erstellt ein Klassenobjekt für die neu abgeleitete aus einem angegebenen Objekt.    
  
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
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`ppNewClass`  
[out] Erhält den Zeiger auf das neue Objekt der Klasse Definition an. Wenn ein Fehler auftritt, wird ein neues Objekt nicht zurückgegeben, und `ppNewClass` ist der linke unverändert bleiben sollen. Der Wert darf nicht sein `null`.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Ein allgemeiner Fehler ist aufgetreten. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Es wurde eine ungültige Operation, z. B. Erstellen einer Klasse aus einer Instanz angefordert. |
| `WBEM_E_INCOMPLETE_CLASS` | Die Quellklasse wurde nicht vollständig definiert oder bei der Verwaltung von Windows registriert werden, damit eine neue abgeleitete Klasse nicht zulässig ist. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | `ppNewClass` ist `null`. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) Methode.

`ptr`muss eine Definition einer Klasse, die die übergeordnete Klasse des Objekts erzeugten wird. Das zurückgegebene Objekt ist eine Unterklasse des aktuellen Objekts.

Das neue Objekt im zurückgegebenen `ppNewClass` wird automatisch eine Unterklasse des aktuellen Objekts. Dieses Verhalten kann nicht überschrieben werden. Es gibt keine andere Methode aus, die durch den Unterklassen (abgeleitete Klassen) erstellt werden können.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
