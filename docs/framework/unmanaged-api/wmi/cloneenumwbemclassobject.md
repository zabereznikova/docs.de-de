---
title: Cloneenumwbemclassobject-Funktion (Referenz zur nicht verwalteten API)
description: Die cloneenumwbemclassobject-Funktion erstellt eine logische Kopie eines Enumerators.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1605314f94fd82d2a2cd7be105dde9e273f607bc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798700"
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject-Funktion
Erstellt eine logische Kopie eines Enumerators unter Beibehaltung der aktuellen Position in einer Enumeration.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```

## <a name="parameters"></a>Parameter

`ppEnum`\
vorgenommen Empfängt einen Zeiger auf ein neues [ienumwbemclassobject-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`\
in Die Autorisierungs Ebene.

`impLevel`\
in Die Ebene des Identitäts Wechsels.

`pCurrentEnumWbemClassObject`\
vorgenommen Ein Zeiger auf die Instanz von [ienumwbemclassobject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) , die geklont werden soll.

`strUser`\
in Der Benutzername. Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.

`strPassword`\
in Das Kennwort. Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.

`strAuthority`[in] der Domänen Name des Benutzers. Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufrufe der [ienumwbemclassobject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) -Methode.

Mit dieser Methode wird nur eine "bestmögliche" Kopie erstellt. Aufgrund der dynamischen Natur vieler CIM-Objekte ist es möglich, dass der neue Enumerator nicht denselben Satz von Objekten aufzählt wie der Quell Enumerator.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter der [ienumwbemclassobject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) -Methode.

## <a name="requirements"></a>Anforderungen
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Header:** WMINet_Utils.idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
