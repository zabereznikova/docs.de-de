---
title: Putclasswmi-Funktion (Referenz zur nicht verwalteten API)
description: Die putclasswmi-Funktion erstellt eine neue Klasse oder aktualisiert eine vorhandene.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fcf879705135e0093868b48580a37f9d46aa594
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798380"
---
# <a name="putclasswmi-function"></a>Putclasswmi-Funktion

Erstellt eine neue Klasse oder aktualisiert eine vorhandene Klasse.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a>Parameter

`pObject`\
in Ein Zeiger auf eine gültige Klassendefinition. Er muss mit allen erforderlichen Eigenschafts Werten ordnungsgemäß initialisiert werden.

`lFlags`\
in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken. Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Wenn diese Einstellung festgelegt ist, speichert WMI keine Qualifizierer mit der geänderten Konfiguration. <br> Wenn nicht festgelegt, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist, und alle Qualifizierer werden mit dieser Instanz gespeichert. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Erstellen Sie die Klasse, wenn Sie nicht vorhanden ist, oder überschreiben Sie Sie, falls Sie bereits vorhanden ist. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aktualisieren Sie die-Klasse. Die Klasse muss vorhanden sein, damit der-Befehl erfolgreich ausgeführt werden konnte. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Erstellen Sie die-Klasse. Der-Rückruf schlägt fehl, wenn die Klasse bereits vorhanden ist. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das-Flag verursacht einen semisynchronen-Rückruf. |
| `WBEM_FLAG_OWNER_UPDATE` | 0x10000 | Pushanbieter müssen dieses Flag angeben, wenn `PutClassWmi` aufgerufen wird, um anzugeben, dass diese Klasse geändert wurde. |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | Ermöglicht es, eine Klasse zu aktualisieren, wenn keine abgeleiteten Klassen und keine Instanzen dieser Klasse vorhanden sind. Sie ermöglicht auch Updates in allen Fällen, wenn die Änderung nur an wichtigen Qualifizierern wie dem Beschreibungs Qualifizierer vorgenommen wird. Wenn die Klasse über Instanzen oder Änderungen an wichtigen Qualifizierern verfügt, schlägt die Aktualisierung fehl. |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0x20 | Ermöglicht das Aktualisieren von Klassen auch dann, wenn untergeordnete Klassen vorhanden sind, wenn die Änderung keine Konflikte mit untergeordneten Klassen verursacht. Beispielsweise kann mit diesem Flag eine neue Eigenschaft zur Basisklasse hinzugefügt werden, die nicht zuvor in einer der untergeordneten Klassen erwähnt wurde. Wenn die Klasse über Instanzen verfügt, tritt bei der Aktualisierung ein Fehler auf. |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0x40 | erzwingt das Aktualisieren von Klassen, wenn widersprüchliche untergeordnete Klassen vorhanden sind. Beispielsweise erzwingt dieses Flag ein Update, wenn ein Klassen Qualifizierer in einer untergeordneten Klasse definiert ist, und die Basisklasse versucht, denselben Qualifizierer hinzuzufügen, der einen Konflikt mit dem vorhandenen Qualifizierer verursacht. Im Force-Modus wird der Konflikt von TIS behoben, indem der widersprüchliche Qualifizierer in der untergeordneten Klasse gelöscht wird. |

`pCtx`\
in Normalerweise ist `null`dieser Wert. Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Klassen bereitstellt.

`ppCallResult`\
vorgenommen Wenn `null`der Wert ist, wird dieser Parameter nicht verwendet. Wenn `lFlags` `WBEM_S_NO_ERROR`enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, gibt die Funktion sofort mit zurück. Der `ppCallResult` -Parameter empfängt einen Zeiger auf ein neues [iwbemcallresult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) -Objekt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Der Benutzer verfügt nicht über die Berechtigung, Klassen zu erstellen oder zu ändern. |
| `WBEM_E_FAILED` | 0x80041001 | Ein nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | Die angegebene Klasse ist ungültig. In der Regel gibt dies `pObject` an, dass ein Instanzobjekt angibt. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | Der angegebene Klassenname ist ungültig. |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | Es wurde versucht, eine Änderung vorzunehmen, durch die eine Unterklasse ungültig wird. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Das `WBEM_FLAG_CREATE_ONLY` Flag wurde angegeben, aber die Klasse ist bereits vorhanden. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY`wurde in `lFlags`angegeben, und die Klasse wurde nicht gefunden. |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | Die erforderlichen Eigenschaften für Klassen wurden nicht alle festgelegt. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich angehalten und neu gestartet. Ruft [connectserverwmi](connectserverwmi.md) erneut auf. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [IWbemServices::P utclass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) -Methode.

Der Benutzer kann keine Klassen erstellen, deren Namen mit einem Unterstrich beginnen oder enden.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
