---
title: Putmethod-Funktion (Referenz zur nicht verwalteten API)
description: Die Putmethod-Funktion erstellt eine-Methode.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1d409507de593cf198fe87340eece6820eaefc63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127337"
---
# <a name="putmethod-function"></a>Putmethod-Funktion
Erstellt eine Methode.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszName`  
in Der Name der zu erstellenden Methode. 

`lFlags`  
[in]: Reserviert Dieser Parameter muss 0 sein.

`pSignatureIn`  
in Ein Zeiger auf eine Kopie der [__Parameters-System Klasse](/windows/desktop/WmiSdk/--parameters) , die die `in` Parameter für die Methode enthält. Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.  

`pSignatureOut`  
in  Ein Zeiger auf eine Kopie der [__Parameters-System Klasse](/windows/desktop/WmiSdk/--parameters) , die die `out` Parameter für die Methode enthält. Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Mindestens ein Parameter ist ungültig. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Der in den *pinsignature* -und *poutsignature* -Objekten angegebene `[in, out]`-Methoden Parameter verfügt über unterschiedliche Qualifizierer.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Bei einem Methoden Parameter fehlt die Spezifikation des **ID** -Qualifizierers. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Die ID-Reihe, die den Methoden Parametern zugewiesen ist, ist nicht aufeinander folgt oder beginnt nicht bei 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Der Rückgabewert einer Methode hat einen **ID** -Qualifizierer. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Es wurde versucht, einen vorhandenen Methodennamen aus einer übergeordneten Klasse wiederzuverwenden, und die Signaturen stimmen nicht ab. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) -Methode.

Dieser Methoden Aufrufwert wird nur unterstützt, wenn `ptr` eine CIM-Klassendefinition ist. Die Methoden Bearbeitung ist nicht in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeigern verfügbar, die auf CIM-Instanzen verweisen.

Benutzer können keine Methoden erstellen, deren Namen mit einem Unterstrich beginnen oder enden. Dies ist für System Klassen und-Eigenschaften reserviert.

Für eine Methode werden die Parameter "`in`" und "`out`" als Eigenschaften in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Objekten beschrieben.

Ein `[in/out]`-Parameter kann definiert werden, indem Sie die gleiche Eigenschaft zu beiden Objekten hinzufügen, auf die der `pInSignature`-und `pOutSignature`-Parameter verweist. In diesem Fall haben die Eigenschaften denselben **ID** -qualifiziererwert.

Jede Eigenschaft in einem [__Parameters](/windows/desktop/WmiSdk/--parameters) -Klassenobjekt, das nicht `ReturnValue` ist, muss über einen **ID** -Qualifizierer verfügen, einem NULL basierten numerischen Wert, der die Reihenfolge angibt, in der die Parameter angezeigt werden. Zwei Parameter können nicht denselben **ID** -Wert haben, und es kann kein **ID** -Wert übersprungen werden. Wenn eine Bedingung auftritt, gibt die `PutMethod`-Funktion `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`zurück.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter der [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) -Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
