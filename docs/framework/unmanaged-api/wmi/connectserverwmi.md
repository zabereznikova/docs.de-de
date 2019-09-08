---
title: Connectserverwmi-Funktion (Referenz zur nicht verwalteten API)
description: Die connectserverwmi-Funktion verwendet DCOM, um eine Verbindung mit einem WMI-Namespace herzustellen.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ebb268dcee877f4e9aea0c88852333897030dd1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798756"
---
# <a name="connectserverwmi-function"></a>Connectserverwmi-Funktion

Erstellt über DCOM eine Verbindung mit einem WMI-Namespace auf einem angegebenen Computer.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel,
   [in] DWORD              authLevel
);
```

## <a name="parameters"></a>Parameter

`strNetworkResource`\
in Zeiger auf ein gültiges `BSTR` -Objekt, das den Objekt Pfad des korrekten WMI-Namespace enthält. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".

`strUser`\
in Ein Zeiger auf einen gültigen `BSTR` , der den Benutzernamen enthält. Ein `null` -Wert gibt den aktuellen Sicherheitskontext an. Wenn der Benutzer aus einer anderen Domäne als die aktuelle Domäne gehört, `strUser` kann auch die Domäne und den Benutzernamen durch einen umgekehrten Schrägstrich getrennt enthalten. `strUser`kann auch im UPN-Format (User Principal Name) vorliegen, z `userName@domainName`. b. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".

`strPassword`\
in Ein Zeiger auf einen gültigen `BSTR` , der das Kennwort enthält. `null` Gibt den aktuellen Sicherheitskontext an. Eine leere Zeichenfolge ("") gibt ein gültiges Kennwort der Länge 0 (null) an.

`strLocale`\
in Ein Zeiger auf einen gültigen `BSTR` , der das richtige Gebiets Schema für den Informations Abruf angibt. Bei Microsoft-Gebiets Schema Bezeichnern ist das Format der Zeichenfolge "\_MS*xxx*", wobei *xxx* eine Zeichenfolge in Hexadezimal Form ist, die den Gebiets Schema Bezeichner (LCID) angibt. Wenn ein ungültiges Gebiets Schema angegeben wird, gibt `WBEM_E_INVALID_PARAMETER` die Methode zurück, mit Ausnahme von Windows 7, wobei stattdessen das Standard Gebiets Schema des Servers verwendet wird. Wenn "NULL1", wird das aktuelle Gebiets Schema verwendet.

`lSecurityFlags`\
in Flags, die an die `ConnectServerWmi` Methode übergeben werden sollen. Der Wert 0 (null) für diesen Parameter führt dazu, dass nur dann `ConnectServerWmi` zurückgegeben wird, nachdem eine Verbindung mit dem Server hergestellt wurde. Dies könnte dazu führen, dass eine Anwendung nicht unbegrenzt reagiert, wenn der Server beschädigt ist. Die anderen gültigen Werte lauten:

| Konstante  | Wert  | Beschreibung  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | Für die interne Verwendung vorgesehen. Nicht verwenden. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi`gibt zwei Minuten oder weniger zurück. |

`strAuthority`\
in Der Domänen Name des Benutzers. Die folgenden Werte sind möglich:

| Wert | Beschreibung |
|---------|---------|
| leer | Die NTLM-Authentifizierung wird verwendet, und die NTLM-Domäne des aktuellen Benutzers wird verwendet. Wenn `strUser` die Domäne angibt (der empfohlene Speicherort), darf Sie hier nicht angegeben werden. Die Funktion gibt `WBEM_E_INVALID_PARAMETER` zurück, wenn Sie die Domäne in beiden Parametern angeben. |
| Kerberos:*Prinzipal Name* | Die Kerberos-Authentifizierung wird verwendet, und dieser Parameter enthält einen Kerberos-Prinzipal Namen. |
| Ntlmdomain:*Domänen Name* | Die NT-LAN-Manager-Authentifizierung wird verwendet, und dieser Parameter enthält einen NTLM-Domänen Namen. |

`pCtx`\
in Normalerweise ist `null`dieser Parameter. Andernfalls handelt es sich um einen Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Objekt, das von einem oder mehreren dynamischen Klassen Anbietern benötigt wird.

`ppNamespace`\
vorgenommen Wenn die Funktion zurückgibt, empfängt einen Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das an den angegebenen Namespace gebunden ist. `null` Wenn ein Fehler vorliegt, wird festgelegt, dass auf den Wert verweist.

`impLevel`\
in Die Ebene des Identitäts Wechsels.

`authLevel`\
in Die Autorisierungs Ebene.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Rückruf für die [IWBEMLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) -Methode.

Für den lokalen Zugriff auf den Standard Namespace `strNetworkResource` kann ein einfacher Objekt Pfad sein: "root\default" oder "\\.\root\default". Für den Zugriff auf den Standard Namespace auf einem Remote Computer mit com oder Microsoft-kompatiblem Netzwerk verwenden Sie den Computer\\Namen: "myserver\root\default". Der Computername kann auch ein DNS-Name oder eine IP-Adresse sein. Die `ConnectServerWmi` Funktion kann auch mit IPv6-Adressen eine Verbindung mit Computern herstellen, auf denen IPv6 ausgeführt wird.

`strUser`darf keine leere Zeichenfolge sein. Wenn die Domäne in `strAuthority`angegeben ist, darf Sie nicht auch in `strUser`enthalten sein, oder die Funktion gibt `WBEM_E_INVALID_PARAMETER`zurück.

## <a name="requirements"></a>Anforderungen

 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Header:** WMINet_Utils.idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
