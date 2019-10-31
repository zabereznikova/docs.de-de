---
title: QualifierSet_Get-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Get-Funktion Ruft einen benannten Qualifizierer ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: dc09cd30c43647fa00cccc1dc00da4f8de367e84
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127277"
---
# <a name="qualifierset_get-function"></a>QualifierSet_Get-Funktion
Ruft den angegebenen benannten Qualifizierer ab.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`   
in Dieser Parameter wird nicht verwendet.

`ptr`   
in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.

`wszName`   
in Der Name des Qualifizierers, dessen Wert angefordert wird.

`lFlags`   
[in]: Reserviert Dieser Parameter muss 0 sein.

`pVal`   
vorgenommen Bei Erfolg der richtige Typ und Wert für den Qualifizierer. Wenn die Funktion fehlschlägt, wird die `VARIANT`, auf die `pVal` verweist, nicht geändert. Wenn dieser Parameter `null`ist, wird der-Parameter ignoriert.

`plFlavor`   
vorgenommen Ein Zeiger auf einen Long-Wert, der die qualifizierungsbits für den angeforderten Qualifizierer empfängt. Wenn keine Informationen zur Konfiguration erwünscht sind, kann dieser Parameter `null`werden. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 angezeigt | Der angegebene Qualifizierer ist nicht vorhanden. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) -Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
