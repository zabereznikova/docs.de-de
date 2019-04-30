---
title: GetObjectText-Funktion (Referenz zur nicht verwalteten API)
description: Die GetObjectText-Funktion gibt ein Text-Rendering eines Objekts in MOF-Syntax.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d34cb399ac0e8780c442eeb2e95cebfd0a22ca02
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040572"
---
# <a name="getobjecttext-function"></a>GetObjectText-Funktion
Gibt eine Textrendering des Objekts in der Managed Object Format (MOF)-Syntax zurück.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`lFlags`  
[in] Normalerweise 0. Wenn `WBEM_FLAG_NO_FLAVORS` (oder 0 x 1) angegeben wird, Qualifizierer werden ohne Weitergabe oder Art Informationen enthalten.

`pstrObjectText`   
[out] Ein Zeiger auf eine `null` auf Eintrag. Bei der Rückgabe eine neu zugeordnete `BSTR` , der eine MOF-Syntax die Darstellung des Objekts enthält.  

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es wurde ein allgemeiner Fehler. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) Methode.

Der MOF-Text zurückgegeben, enthält nicht alle Informationen über das Objekt, aber nur genügend Informationen für die MOF-Compiler, um das ursprüngliche Objekt neu erstellen zu können. Beispielsweise sind keine weitergegebenen Qualifizierer oder die Eigenschaften der übergeordneten Klasse enthalten.

Der folgende Algorithmus wird verwendet, um den Text der Parameter einer Methode zu rekonstruieren:

1. Parameter werden in der Reihenfolge ihrer Bezeichnerwerte resequenced.
1. Parameter, die als angegeben sind `[in]` und `[out]` werden in einem einzigen Parameter kombiniert.
 
`pstrObjectText` muss ein Zeiger auf eine `null` , wenn die Funktion aufgerufen wird; es muss auf eine Zeichenfolge, die vor dem Methodenaufruf gültig ist, da der Zeiger nicht freigegeben wird, nicht zu verweisen.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
