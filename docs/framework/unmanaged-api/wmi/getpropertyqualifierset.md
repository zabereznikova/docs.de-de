---
title: Getpropertyqualifierset-Funktion (Referenz zur nicht verwalteten API)
description: Die getpropertyqualifierset-Funktion Ruft den Qualifizierer Satz für eine Eigenschaft ab.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7bce241d10051e4c6be94cdfa40de23773fb0bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798472"
---
# <a name="getpropertyqualifierset-function"></a>Getpropertyqualifierset-Funktion

Ruft den Qualifizierer ab, der für eine bestimmte Eigenschaft festgelegt ist.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszMethod`\
in Der Eigenschaftsname. `wszProperty`muss auf einen gültigen `LPCWSTR`zeigen.

`ppQualSet`\
vorgenommen Empfängt den Schnittstellen Zeiger, der den Zugriff auf die Qualifizierer der Eigenschaft zulässt. `ppQualSet` darf nicht `null` sein. Wenn ein Fehler auftritt, wird kein neues Objekt zurückgegeben, und der Zeiger wird so festgelegt, `null`dass er auf verweist.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode ist nicht vorhanden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein-Parameter `null`ist. |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | Die Funktion versucht, Qualifizierer einer System Eigenschaft zu erhalten. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: getpropertyqualifierset](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) -Methode.

Ein Aufrufe dieser Funktion wird nur unterstützt, wenn das aktuelle Objekt eine CIM-Klassendefinition ist. Die Methoden Bearbeitung ist für [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeiger, die auf CIM-Instanzen verweisen, nicht verfügbar.

Da jede Methode über eigene Qualifizierer verfügen kann, ermöglicht der [iwbemqualifierset-Zeiger dem Aufrufer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) , diese Qualifizierer hinzuzufügen, zu bearbeiten oder zu löschen.

Da Systemeigenschaften keine Qualifizierer aufweisen, gibt `WBEM_E_SYSTEM_PROPERTY` die Funktion zurück, wenn Sie versuchen, einen [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Zeiger für eine System Eigenschaft abzurufen.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
