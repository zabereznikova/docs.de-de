---
title: Putinstancewmi-Funktion (Referenz zur nicht verwalteten API)
description: Die putinstancewmi-Funktion erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b33f31d69c64ce520580c29f1014c058c78d0953
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127357"
---
# <a name="putinstancewmi-function"></a>Putinstancewmi-Funktion

Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse. Die Instanz wird in das WMI-Repository geschrieben.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a>Parameter

`pInst`\
in Ein Zeiger auf die zu schreibende-Instanz.

`lFlags`\
in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken. Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Wenn diese Einstellung festgelegt ist, speichert WMI keine Qualifizierer mit der **geänderten** Konfiguration. <br> Wenn nicht festgelegt, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist, und alle Qualifizierer werden mit dieser Instanz gespeichert. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Erstellen Sie die Instanz, wenn Sie nicht vorhanden ist, oder überschreiben Sie Sie, falls Sie bereits vorhanden ist. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aktualisieren Sie die-Instanz. Die Instanz muss vorhanden sein, damit der-Befehl erfolgreich ausgeführt werden konnte. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Erstellen Sie die-Instanz. Der-Rückruf schlägt fehl, wenn die Instanz bereits vorhanden ist. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das-Flag verursacht einen semisynchronen-Rückruf. |

`pCtx`\
in In der Regel ist dieser Wert `null`. Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Klassen bereitstellt.

`ppCallResult`\
vorgenommen Wenn `null`, wird dieser Parameter nicht verwendet. Wenn `lFlags` `WBEM_FLAG_RETURN_IMMEDIATELY`enthält, gibt die Funktion sofort mit `WBEM_S_NO_ERROR`zurück. Der `ppCallResult`-Parameter empfängt einen Zeiger auf ein neues [iwbemcallresult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) -Objekt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Der Benutzer verfügt nicht über die Berechtigung zum Aktualisieren einer Instanz der angegebenen Klasse. |
| `WBEM_E_FAILED` | 0x80041001 | Ein nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | Die Klasse, die diese Instanz unterstützt, ist ungültig. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | eine `null` wurde für eine Eigenschaft angegeben, die nicht `null`werden kann, z. b. eine, die durch einen **indizierten** oder **Not_Null** -Qualifizierer gekennzeichnet ist. |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | Die angegebene Instanz ist ungültig. (Wenn Sie beispielsweise `PutInstanceWmi` mit einer-Klasse aufrufen, wird dieser Wert zurückgegeben.) |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Das `WBEM_FLAG_CREATE_ONLY`-Flag wurde angegeben, aber die Instanz ist bereits vorhanden. |
| `WBEM_E_NOT_FOUND` | 0x80041002 angezeigt | in `lFlags`wurde `WBEM_FLAG_UPDATE_ONLY` angegeben, aber die Instanz ist nicht vorhanden. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich angehalten und neu gestartet. Ruft [connectserverwmi](connectserverwmi.md) erneut auf. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Rückruf für die [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) -Methode.

Die `PutInstanceWmi`-Funktion unterstützt das Erstellen von-Instanzen und das Aktualisieren von Instanzen vorhandener Klassen.  Abhängig davon, wie der `pCtx`-Parameter festgelegt wird, werden entweder einige oder alle Eigenschaften der-Instanz aktualisiert.

Wenn die-Instanz, auf die `pInst` verweist, zu einer Unterklasse gehört, ruft die Windows-Verwaltung alle Anbieter auf, die für die Klassen verantwortlich sind, von denen die Unterklasse abgeleitet ist. Alle diese Anbieter müssen erfolgreich sein, damit die ursprüngliche `PutInstanceWmi` Anforderung erfolgreich ausgeführt wird. Der Anbieter, der die oberste Klasse in der Hierarchie unterstützt, wird zuerst aufgerufen. Die Aufruf Reihenfolge wird mit der Unterklasse der obersten Klasse fortgesetzt und geht von oben nach unten fort, bis die Windows-Verwaltung den Anbieter für die Klasse erreicht hat, auf die `pInst`verweist.
Die Windows-Verwaltung Ruft die Anbieter für keine der untergeordneten Klassen einer-Instanz auf.

Wenn eine Anwendung eine Instanz aktualisieren muss, die zu einer Klassenhierarchie gehört, muss der `pInst`-Parameter auf die Instanz verweisen, die die zu ändernden Eigenschaften enthält. Das heißt, eine Ziel Instanz, die zu **ClassB**gehört. Die **ClassB** -Instanz ist von **ClassA**abgeleitet, und **ClassA** definiert die Eigenschafts **propa**. Wenn eine Anwendung eine Änderung am Wert von **propa** in der **ClassB** -Instanz vornehmen möchte, muss `pInst` auf diese Instanz und nicht auf eine Instanz von **ClassA**festgelegt werden.

Das Aufrufen von `PutInstanceWmi` für eine Instanz einer abstrakten Klasse ist nicht zulässig.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils. idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
