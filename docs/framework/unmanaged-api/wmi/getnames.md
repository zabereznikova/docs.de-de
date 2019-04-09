---
title: GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion "GetNames" Ruft den Namen der Eigenschaften eines Objekts ab.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f664edf29e5d2f9ec4e523aa7f7b204cf999e01b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202650"
---
# <a name="getnames-function"></a>GetNames-Funktion
Ruft eine Teilmenge oder alle Namen der Eigenschaften eines Objekts ab. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`wszQualifierName`  
[in] Ein Zeiger auf ein gültiges `LPCWSTR` , einen Qualifizierer-Namen, die ausgeführt wird als Teil eines Filters angibt. Weitere Informationen finden Sie unter den ["Hinweise"](#remarks) Abschnitt. Dieser Parameter kann `null` sein. 

`lFlags`  
[in] Eine Kombination von Bitfeldern. Weitere Informationen finden Sie unter den ["Hinweise"](#remarks) Abschnitt.

`pQualifierValue`   
[in] Ein Zeiger auf ein gültiges `VARIANT` -Struktur mit einem Filterwert initialisiert. Dieser Parameter kann `null` sein. 

`pstrNames`  
[out] Ein `SAFEARRAY` Struktur, die Eigenschaftennamen enthält. Dieser Parameter muss bei einem Eintrag sein immer ein Zeiger auf `null`. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es wurde ein allgemeiner Fehler. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Eine oder mehrere Parameter sind ungültig, oder es wurde eine falsche Kombination von Flags und Parameter angegeben. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) Methode.

Der benannte zurückgegeben werden durch eine Kombination von Flags und Parameter gesteuert. Die Funktion kann z. B. die Namen aller Eigenschaften oder nur die Namen der wichtigsten Eigenschaften zurück.  In der primäre Filter angegeben wird die `lFlags` Parameter und die anderen Parameter hängen sie.

Das Flag-Werte im `lFlags` Bitfelder werden

Die Flags, die als übergeben werden können die `lEnumFlags` Argument sind Bitfeldern, die in definierten die *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code.  Sie können einen Flag aus jeder Gruppe mit einem Flag aus einer anderen Gruppe kombinieren. Allerdings sind Flags aus der gleichen Gruppe sich gegenseitig ausschließende. 

| Gruppe 1-flags |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Geben Sie bei allen Eigenschaftsnamen zurück. `strQualifierName` und `pQualifierVal` werden nicht verwendet. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Nur Eigenschaften, die einen Qualifizierer, der den Namen trägt Zurückgeben der `strQualifierName` Parameter. Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Zurückgeben von Eigenschaften, die nicht über einen Qualifizierer mit dem vom angegebenen Namen verfügen die `strQualifierName` Parameter. Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Nur Eigenschaften, die einen Qualifizierer, der den Namen trägt Zurückgeben der `wszQualifierName` Parameter und außerdem einen Wert, der identisch mit dem angegeben wird, indem die `pQualifierVal` Struktur. Wenn dieses Flag verwendet wird, müssen Sie angeben, sowohl eine `wszQualifierName` und `pQualifierValue`. |

| Gruppe 2-flags |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Zurückgeben Sie, nur die Namen der Eigenschaften, die die Schlüssel zu definieren. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Rückgabe nur Eigenschaftennamen, die Objektverweise sind. |

| Gruppe 3-flags |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Zurückgeben von nur für den Eigenschaftennamen, die am stärksten abgeleitete Klasse angehören. Ausschließen von Eigenschaften aus der übergeordneten Klassen. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Zurückgeben von nur für den Eigenschaftennamen, die die übergeordneten Klassen angehören. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Geben Sie nur die Namen der Systemeigenschaften zurück. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Geben Sie nur die Namen der Eigenschaften, die nicht zum System zurück. |

Die Funktion weist immer einen neuen `SAFEARRAY` zurückgegeben `WBEM_S_NO_ERROR`, und `pstrNames` ist immer festgelegt, um darauf zu verweisen. Das zurückgegebene Array kann 0 Elemente verfügen, wenn keine Eigenschaften mit den angegebenen Filtern übereinstimmen. Wenn die Funktion einen Wert zurückgibt, die als `WBM_S_NO_ERROR`, ein neues `SAFEARRAY` Struktur wird nicht zurückgegeben.
 
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
