---
title: ExecQueryWmi-Funktion (Referenz zur nicht verwalteten API)
description: ExecQueryWmi-Funktion führt eine Abfrage zum Abrufen von Objekten.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc22edf51cbd726b69dff3da2f0540b2c3864f2e
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929625"
---
# <a name="execquerywmi-function"></a>ExecQueryWmi-Funktion
Führt eine Abfrage zum Abrufen von Objekten.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExecQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a>Parameter

`strQueryLanguage`    
[in] Eine Zeichenfolge mit der gültigen Abfragesprache, die von der Windows-Verwaltung unterstützt. Es muss "WQL", das Akronym für WMI-Abfragesprache.

`strQuery`  
[in] Der Text der Abfrage. Dieser Parameter darf nicht sein `null`.

`lFlags`   
[in] Eine Kombination von Flags, die das Verhalten dieser Funktion zu beeinflussen. Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code: 

| Konstante | Wert  | Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Wenn festgelegt ist, die Funktion ruft ab, die ergänzende Qualifizierer, die in der lokalisierten Namespace des Gebietsschemas für die aktuelle Verbindung gespeichert. <br/> Wenn dies nicht festgelegt ist, die Funktion ruft nur die Qualifizierer, die in der unmittelbaren Namespace gespeichert. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das Flag wird halbsynchron aufgerufen. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Die Funktion gibt einen Enumerator vorwärts gerichtete. In der Regel vorwärts-Enumeratoren sind schneller, und verwenden Sie weniger Arbeitsspeicher als konventionelle Enumeratoren, aber sie ermöglichen keine Aufrufe von [Klon](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI behält Zeiger auf Objekte in der Enumration, bis sie freigegeben werden. | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0 x 100 | Stellt sicher, dass alle zurückgegebenen Objekte haben genug Informationen darin, Eigenschaften, wie z. B. **__PATH**, **__RELPATH**, und **__SERVER**, sind nicht `null`. |
| `WBEM_FLAG_PROTOTYPE` | 2 | Dieses Flag wird zum Erstellen von Prototypen verwendet. Die Abfrage nicht ausgeführt, und es wird stattdessen ein Objekt, das aussieht wie ein typisches Ergebnis-Objekt zurückgegeben. |
| `WBEM_FLAG_DIRECT_READ` | 0 x 200 | Bewirkt, dass direkter Zugriff auf den Anbieter für die Klasse, die unabhängig von der übergeordneten Klasse oder Unterklassen angegeben. |

Die empfohlene Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY` für eine optimale Leistung.

`pCtx`  
[in] Dieser Wert in der Regel ist `null`. Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderten Klassen bereitstellt. 

`ppEnum`  
[out] Wenn kein Fehler auftritt, empfängt den Zeiger auf der Enumerator, der dem Aufrufer zum Abrufen von Instanzen im Resultset der Abfrage ermöglicht. Die Abfrage kann es sich um ein Resultset mit NULL-Instanzen aufweisen. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`authLevel`  
[in] Die Autorisierungsebene.

`impLevel` [in] Die Ebene des Identitätswechsels.

`pCurrentNamespace`   
[in] Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.

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
| `WBEM_E_ACCESS_DENIED` | 0 x 80041003 | Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann. |
| `WBEM_E_FAILED` | 0 x 80041001 | Ein Unbekannter Fehler aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Die Abfrage musste ein Syntaxfehler aufgetreten. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Die angeforderte Abfragesprache wird nicht unterstützt. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Die Abfrage ist zu komplex. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Die Abfrage gibt eine Klasse, die nicht vorhanden ist. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) Methode.

Diese Funktion verarbeitet die Abfrage der `strQuery` Parameter und erstellt einen Enumerator über die der Aufrufer die Ergebnisse der Abfrage zugreifen kann. Der Enumerator ist ein Zeiger auf ein [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) -Schnittstelle, die Abfrage Ergebnisse sind Instanzen der Klassenobjekte, die über verfügbar gemacht der [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Schnittstelle.

Bestehen Einschränkungen in Bezug auf die Anzahl der `AND` und `OR` Schlüsselwörter, die in WQL-Abfragen verwendet werden können. Große Anzahl von WQL-Schlüsselwörter, die verwendet werden, in eine komplexe Abfrage kann dazu führen, dass WMI Zurückgeben der `WBEM_E_QUOTA_VIOLATION` (oder 0x8004106c) Fehlercode als ein `HRESULT` Wert. Das Limit von WQL-Schlüsselwörter, hängt davon ab, wie komplex die Abfrage ist.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
