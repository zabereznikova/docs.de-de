---
title: QualifierSet_EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_EndEnumeration beendet eine Enumeration.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e24acdde486f377cc9187aac088ce7a611cd4eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460743"
---
# <a name="qualifiersetendenumeration-function"></a>QualifierSet_EndEnumeration-Funktion
Beendet die Enumeration, die mit einem Aufruf von begonnen der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) Funktion.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`   
[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.

## <a name="return-value"></a>Rückgabewert

Der folgende Wert, der von dieser Funktion zurückgegebenen wird definiert, der *WbemCli.h* Header-Datei, oder Sie können es als definieren eine Konstante in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) Methode.

Dieser Aufruf wird empfohlen, jedoch nicht erforderlich. Es gibt sofort die Enumeration zugeordnete Ressourcen frei.

## <a name="requirements"></a>Anforderungen  

**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
**Header:** WMINet_Utils.idl  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
