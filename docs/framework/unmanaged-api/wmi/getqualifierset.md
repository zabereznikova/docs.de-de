---
title: GetQualifierSet-Funktion (Nicht verwaltete API-Referenz)
description: Die GetQualifierSet-Funktion ruft den Qualifizierersatz für eine Klasse oder Instanz ab.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176772"
---
# <a name="getqualifierset-function"></a>GetQualifierSet-Funktion
Ruft den Qualifizierer ab, der für eine Klasseninstanz oder eine Klassendefinition festgelegt ist.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`ppQualSet`  
[out] Empfängt den Schnittstellenzeiger, der den Zugriff auf die Qualifizierer des Klassenobjekts ermöglicht. `ppQualSet` darf nicht `null` sein. Wenn ein Fehler auftritt, wird kein neues Objekt zurückgegeben, und der Zeiger bleibt unverändert.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeines Versagen aufgetreten. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode ist nicht vorhanden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter `null`ist . |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetQualifierSet-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)

Mit dem [IWbemQualifierSet-Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) kann der Aufrufer diese Qualifizierer hinzufügen, bearbeiten oder löschen. Solche hinzugefügten, bearbeiteten oder gelöschten Qualifizierer gelten für die gesamte Instanz- oder Klassendefinition.

## <a name="requirements"></a>Requirements (Anforderungen)  
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
