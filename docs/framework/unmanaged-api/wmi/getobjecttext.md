---
title: GetObjectText-Funktion (Nicht verwaltete API-Referenz)
description: Die GetObjectText-Funktion gibt ein Textrendering eines Objekts in der MOF-Syntax zurück.
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
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176785"
---
# <a name="getobjecttext-function"></a>GetObjectText-Funktion
Gibt ein Textrendering des Objekts in der MOF-Syntax (Managed Object Format) zurück.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in] Normalerweise 0. Wenn `WBEM_FLAG_NO_FLAVORS` (oder 0x1) angegeben ist, werden Qualifizierer ohne Vermehrungs- oder Geschmacksinformationen eingeschlossen.

`pstrObjectText`[out] Ein Zeiger auf `null` einen Eintrag. Bei der Rückgabe `BSTR` eine neu zugewiesene, die eine MOF-Syntax-Rendering des Objekts enthält.  

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeines Versagen aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist nicht gültig. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetObjectText-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)

Der zurückgegebene MOF-Text enthält nicht alle Informationen über das Objekt, sondern nur genügend Informationen, damit der MOF-Compiler das ursprüngliche Objekt neu erstellen kann. Beispielsweise sind keine weitergegebenen Qualifizierer oder übergeordneten Klasseneigenschaften enthalten.

Der folgende Algorithmus wird verwendet, um den Text der Parameter einer Methode zu rekonstruieren:

1. Parameter werden in der Reihenfolge ihrer Bezeichnerwerte neu sequenziert.
1. Parameter, die `[in]` als `[out]` Parameter angegeben und zu einem einzelnen Parameter kombiniert werden.

`pstrObjectText`muss ein Zeiger auf `null` ein sein, wenn die Funktion aufgerufen wird; Sie darf nicht auf eine Zeichenfolge verweisen, die vor dem Methodenaufruf gültig ist, da der Zeiger nicht ausgelastt wird.

## <a name="requirements"></a>Requirements (Anforderungen)  
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
