---
title: CloneEnumWbemClassObject-Funktion (Referenz zur nicht verwalteten API)
description: CloneEnumWbemClassObject-Funktion ist eine logische Kopie eines Enumerators.
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
ms.openlocfilehash: 52edc72e3714ceaf8cc92f272da6a374eb324dad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661645"
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject-Funktion
Erstellt eine logische Kopie eines Enumerators unter Beibehaltung der aktuellen Position in einer Enumeration.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
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

`ppEnum`  
[out] Erhält einen Zeiger auf ein neues [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`  
[in] Die Autorisierungsebene.

`impLevel` [in] Die Ebene des Identitätswechsels.

`pCurrentEnumWbemClassObject`  
[out] Ein Zeiger auf die [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) Instanz, geklont zu werden.

`strUser`   
[in] Der Benutzername. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strPassword`   
[in] Das Kennwort. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strAuthority`   
[in] Der Domänenname des Benutzers. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es wurde ein allgemeiner Fehler. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Ist nicht genügend Arbeitsspeicher verfügbar, der Vorgang abgeschlossen werden. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) Methode.

Auf diese Weise wird nur eine "best-Effort" kopieren. Aufgrund der dynamischen Natur der viele CIM-Objekte werden soll ist es möglich, dass der neue Enumerator nicht den gleichen Satz von Objekten als Enumerator aus Quelle aufgelistet werden.  

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter den [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch
- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
