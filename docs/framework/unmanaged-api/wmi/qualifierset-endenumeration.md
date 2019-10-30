---
title: QualifierSet_EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_EndEnumeration-Funktion beendet eine Enumeration.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 82627fa416f71e123ed2c03bae4584e4433310eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127287"
---
# <a name="qualifierset_endenumeration-function"></a>QualifierSet_EndEnumeration-Funktion
Beendet die Enumeration, die mit einem aufrufsbefehl der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) -Funktion gestartet wurde.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`   
in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.

## <a name="return-value"></a>Rückgabewert

Der folgende Wert, der von dieser Funktion zurückgegeben wird, ist in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstante im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) -Methode.

Dieser Befehl wird empfohlen, ist jedoch nicht erforderlich. Es werden sofort die der-Enumeration zugeordneten Ressourcen freigegeben.

## <a name="requirements"></a>Anforderungen  

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
**Header:** WMINet_Utils. idl  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
