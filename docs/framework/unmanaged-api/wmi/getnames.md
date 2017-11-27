---
title: "\"GetNames\"-Funktion (Referenz zur nicht verwalteten API)"
description: Die Funktion "GetNames" Ruft die Namen der Eigenschaften eines Objekts ab.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetNames
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetNames
helpviewer_keywords: GetNames function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2ba2530dd43e6924187c80214d5efa13ebc548de
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="getnames-function"></a>"GetNames"-Funktion
Ruft eine Teilmenge oder aller der Namen der Eigenschaften eines Objekts ab. 

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
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`wszQualifierName`  
[in] Ein Zeiger auf eine gültige `LPCWSTR` , einen Qualifizierer-Namen, der ausgeführt wird als Teil eines Filters angibt. Weitere Informationen finden Sie unter der ["Hinweise"](#remarks) Abschnitt. Dieser Parameter kann `null` sein. 

`lFlags`  
[in] Eine Kombination von Bitfeldern. Weitere Informationen finden Sie unter der ["Hinweise"](#remarks) Abschnitt.

`pQualifierValue`   
[in] Ein Zeiger auf eine gültige `VARIANT` -Struktur mit einem Filterwert initialisiert. Dieser Parameter kann `null` sein. 

`pstrNames`  
[out] Ein `SAFEARRAY` -Struktur, die Eigenschaftsnamen enthält. Dieser Parameter muss auf den Eintrag, werden immer ein Zeiger auf `null`. Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | Ein allgemeiner Fehler ist aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Eine oder mehrere Parameter sind ungültig, oder es wurde eine falsche Kombination von Flags und Parameter angegeben. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) Methode.

Die benannte zurückgegeben werden durch eine Kombination der Flags und Parameter gesteuert. Die Funktion kann z. B. die Namen aller Eigenschaften oder nur die Namen der Schlüsseleigenschaften zurück.  Der primäre Filter wird angegeben, der `lFlags` -Parameter, und die anderen Parameter variiert je nach es.

Das Flag Werte in `lFlags` Bitfelder werden


Die Flags, die als übergeben werden können die `lEnumFlags` Argument sind Bitfelder, die in definiert werden die *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code.  Sie können einen Flag aus jeder Gruppe mit einem Flag aus einer anderen Gruppe kombinieren. Es gibt jedoch Flags aus der gleichen Gruppe sich gegenseitig ausschließende. 

| Gruppe 1-flags |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Geben Sie alle Eigenschaftsnamen zurück. `strQualifierName`und `pQualifierVal` nicht verwendet werden. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Nur Eigenschaften, die einen Qualifizierer mit dem Namen angegeben haben Zurückgeben der `strQualifierName` Parameter. Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Nur Eigenschaften, die keine Qualifizierer mit dem Namen angegeben haben Zurückgeben der `strQualifierName` Parameter. Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Nur Eigenschaften, die einen Qualifizierer mit dem Namen angegeben haben Zurückgeben der `wszQualifierName` Parameter und auch einen Wert identisch mit dem angegeben wird, indem Sie die `pQualifierVal` Struktur. Wenn dieses Flag verwendet wird, müssen Sie beide angeben einer `wszQualifierName` und ein `pQualifierValue`. |

| Gruppe 2-flags |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0 x 4 | Geben Sie nur die Namen von Eigenschaften, die definieren die Schlüssel, zurück. |
|`WBEM_FLAG_REFS_ONLY` | 0 x 8 | Return nur Eigenschaftennamen, die Objektverweise sind. |

| Gruppe 3-flags |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0 x 10 | Geben Sie nur für den Eigenschaftennamen, die auf die am stärksten abgeleitete Klasse gehören zurück. Schließen Sie Eigenschaften aus der übergeordneten Klassen. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0 x 20 | Geben Sie nur für den Eigenschaftennamen, die auf die übergeordneten Klassen gehören zurück. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0 x 30 | Geben Sie nur die Namen der Systemeigenschaften zurück. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0 x 40 | Geben Sie nur die Namen von Eigenschaften nicht zum System zurück. |

Die Funktion weist immer einen neuen `SAFEARRAY` zurückgibt `WBEM_S_NO_ERROR`, und `pstrNames` immer festgelegt ist, um darauf zu verweisen. Das zurückgegebene Array kann 0 Elemente verfügen, wenn keine Eigenschaften mit den angegebenen Filtern übereinstimmen. Wenn die Funktion einen Wert, außer zurückgibt `WBM_S_NO_ERROR`, ein neues `SAFEARRAY` Struktur wird nicht zurückgegeben.
 
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
