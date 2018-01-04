---
title: ExecQueryWmi-Funktion (Referenz zur nicht verwalteten API)
description: "Die ExecQueryWmi-Funktion führt eine Abfrage zum Abrufen von Objekten."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ExecQueryWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ExecQueryWmi
helpviewer_keywords: ExecQueryWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 872109cb0472a8404c492c2867429fe783f898eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
[in] Eine Kombination von Flags, die das Verhalten dieser Funktion beeinflussen. Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code: 

| Konstante | Wert  | Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Wenn festgelegt ist, die Funktion ruft die Qualifizierern in den lokalisierten Namespace des Gebietsschemas für die aktuelle Verbindung gespeichert ab. <br/> Wenn dies nicht festgelegt ist, die Funktion ruft nur die Qualifizierer, die in den unmittelbaren Namespace gespeichert. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0 x 10 | Das Flag wird halbsynchrone aufgerufen. |
| `WBEM_FLAG_FORWARD_ONLY` | 0 x 20 | Die Funktion gibt einen Enumerator Vorwärtscursor. In der Regel nur vorwärts Enumeratoren werden schneller ausgeführt und belegen weniger Speicher als konventionelle Enumeratoren, aber es nicht möglich, dass Aufrufe [Klon](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI behält Zeiger auf Objekte in der Enumration, bis sie veröffentlicht werden. | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0 x 100 | Stellt sicher, dass alle zurückgegebenen Objekte haben genügend Informationen enthalten, Systemeigenschaften wie z. B. **__PATH**, **__RELPATH**, und **__SERVER**, sind nicht `null`. |
| `WBEM_FLAG_PROTOTYPE` | 2 | Dieses Flag wird für die Erstellung von Prototypen verwendet. Die Abfrage wird nicht ausgeführt, und es wird stattdessen ein Objekt, das aussieht wie ein typisches Ergebnis zurückgibt. |
| `WBEM_FLAG_DIRECT_READ` | 0 x 200 | Ursachen direkten Zugriff auf den Anbieter für die Klasse, die unabhängig von der übergeordneten Klasse oder Unterklassen angegeben. |

Die empfohlene Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY` für optimale Leistung zu erzielen.

`pCtx`  
[in] In der Regel wird dieser Wert ist `null`. Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Klassen bereitstellt. 

`ppEnum`  
[out] Wenn kein Fehler auftritt, empfängt den Zeiger auf den Enumerator, der den Aufrufer beim Abrufen von den Instanzen im Resultset der Abfrage ermöglicht. Die Abfrage kann ein Resultset mit 0 (null) Instanzen aufweisen. Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`authLevel`  
[in] Die Autorisierungsebene.

`impLevel`[in] Die Ebene des Identitätswechsels.

`pCurrentNamespace`   
[in] Ein Zeiger auf ein [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) -Objekt, das den aktuellen Namespace darstellt.

`strUser`   
[in] Der Benutzername. Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strPassword`   
[in] Das Kennwort. Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strAuthority`   
[in] Der Domänenname des Benutzers. Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0 x 80041003 | Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann. |
| `WBEM_E_FAILED` | 0 x 80041001 | Nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Die Abfrage hat einen Syntaxfehler. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Die angeforderte Abfragesprache wird nicht unterstützt. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Die Abfrage ist zu komplex. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Die Abfrage gibt eine Klasse, die nicht vorhanden ist. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) Methode.

Diese Funktion verarbeitet die Abfrage der `strQuery` Parameter und erstellt einen Enumerator über die der Aufrufer die Ergebnisse der Abfrage zugreifen kann. Der Enumerator ist ein Zeiger auf ein [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) Schnittstelle; die Abfrage Ergebnisse sind Instanzen von Klassenobjekten bis zur Verfügung gestellt der [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) Schnittstelle.

Begrenzt die Anzahl der `AND` und `OR` Schlüsselwörter, die in der WQL-Abfragen verwendet werden können. Große Anzahl von WQL Schlüsselwörter in eine komplexe Abfrage kann dazu führen, dass WMI zurückzugebenden der `WBEM_E_QUOTA_VIOLATION` (oder 0x8004106c) Fehlercode als ein `HRESULT` Wert. Das Limit von WQL-Schlüsselwörter, hängt davon ab, wie komplex die Abfrage ist.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
