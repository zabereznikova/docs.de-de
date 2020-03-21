---
title: QualifierSet_EndEnumeration -Funktion (Nicht verwaltete API-Referenz)
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
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176746"
---
# <a name="qualifierset_endenumeration-function"></a>QualifierSet_EndEnumeration-Funktion
Beendet die Enumeration, die mit einem Aufruf der [QualifierSet_BeginEnumeration-Funktion](qualifierset-beginenumeration.md) begonnen wurde.  

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
[in] Dieser Parameter ist nicht verwendet.

`ptr`[in] Ein Zeiger auf eine [IWbemQualifierSet-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

## <a name="return-value"></a>Rückgabewert

Der folgende Wert, der von dieser Funktion zurückgegeben wird, ist in der *PseCli.h-Headerdatei* definiert, oder Sie können ihn als Konstante im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::EndEnumeration-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)

Dieser Aufruf wird empfohlen, ist jedoch nicht erforderlich. Es gibt sofort Ressourcen frei, die mit der Enumeration verknüpft sind.

## <a name="requirements"></a>Requirements (Anforderungen)  

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
**Kopfzeile:** WMINet_Utils.idl  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
