---
title: ConnectServerWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die ConnectServerWmi-Funktion verwendet DCOM, um eine Verbindung mit einem WMI-Namespace zu erstellen.
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
ms.openlocfilehash: 163e61eef8a753b5b6470285e5e3ce63789e25a4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44062857"
---
# <a name="connectserverwmi-function"></a>ConnectServerWmi-Funktion
Erstellt über DCOM eine Verbindung mit einem WMI-Namespace auf einem angegebenen Computer.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
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

`strNetworkResource` [in] Zeiger auf eine gültige `BSTR` , die den den richtigen Namespace der WMI-Objektpfad enthält. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`strUser` [in] Ein Zeiger auf ein gültiges `BSTR` , die den Benutzernamen enthält. Ein `null` Wert gibt an, den aktuellen Sicherheitskontext. Wenn der Benutzer aus einer anderen Domäne als der aktuelle Knoten ist `strUser` kann auch die Domäne und den Namen getrennt durch einen umgekehrten Schrägstrich enthalten. `strUser` können auch werden Benutzer Benutzerprinzipalnamen (UPN) formatieren, Suhc als *userName@domainName*. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`strPassword` [in] Ein Zeiger auf ein gültiges `BSTR` , die Kennwort enthält. Ein `null` gibt den aktuellen Sicherheitskontext. Eine leere Zeichenfolge ("") gibt an, ein gültiges Kennwort für die Länge 0 (null).

`strLocale` [in] Ein Zeiger auf ein gültiges `BSTR` , der angibt, dass des richtigen Gebietsschemas für den Abruf von Informationen. Für Microsoft-Gebietsschemabezeichner, die das Format der Zeichenfolge ist "MS\_*Xxx*", wobei *Xxx* ist eine Zeichenfolge im hexadezimalen Format, der den Gebietsschemabezeichner (LCID) angibt. Wenn eine ungültige Gebietsschema angegeben wird, gibt die Methode `WBEM_E_INVALID_PARAMETER` außer auf Windows 7, das Standardgebietsschema des Servers ist, in denen stattdessen verwendet. Wenn "null1, das aktuelle Gebietsschema verwendet wird. 
 
`lSecurityFlags` [in] Flags, die zum Übergeben der `ConnectServerWmi` Methode. Der Wert NULL (0) für diesen Parameter im Aufruf führt `ConnectServerWmi` zurückgeben, nur, nachdem eine Verbindung mit dem Server hergestellt wird. Dadurch kann eine Anwendung, die nicht auf unbestimmte Zeit reagiert, wenn der Server beschädigt ist. Die andere gültige Werte sind:

| Konstante  | Wert  | Beschreibung  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0 x 40 | Für die interne Verwendung vorgesehen. Nicht verwenden. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi` Gibt zurück, die innerhalb von zwei Minuten oder weniger. |

`strAuthority` [in] Der Domänenname des Benutzers. Sie können die folgenden Werte aufweisen:

| Wert | Beschreibung |
|---------|---------|
| leer | NTLM-Authentifizierung verwendet wird, und die NTLM-Domäne des aktuellen Benutzers verwendet. Wenn `strUser` gibt die Domäne (der empfohlene Speicherort), dürfen nicht hier angegeben werden. Die Funktion gibt `WBEM_E_INVALID_PARAMETER` Wenn Sie die Domäne in beide Parameter angeben. |
| Kerberos:*Prinzipalname* | Kerberos-Authentifizierung verwendet wird, und dieser Parameter enthält, ein Kerberos-Prinzipalname. |
| NTLMDOMAIN:*Domänennamen* | NT LAN Manager-Authentifizierung wird verwendet, und dieser Parameter enthält einen NTLM-Domänennamen. |

`pCtx`   
[in] In der Regel ist dieser Parameter ist `null`. Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) Objekt durch eine oder mehrere dynamische Klasse Anbieter erforderlich. 

`ppNamespace`  
[out] Wenn die Funktion zurückgibt, erhält einen Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) Objekt an den angegebenen Namespace gebunden. Festgelegt auf zeigen `null` , wenn ein Fehler auftritt.

`impLevel`  
[in] Die Ebene des Identitätswechsels.

`authLevel`  
[in] Die Autorisierungsebene.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Es wurde ein allgemeiner Fehler. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) Methode.

 Für den lokalen Zugriff auf den Standardnamespace `strNetworkResource` kann ein einfaches Objekt-Pfad: "Root\default" oder "\\.\root\default". Für den Zugriff auf den Standardnamespace auf einem Remotecomputer mithilfe der COM- oder Microsoft-kompatiblen-Netzwerken, den Namen des Computers enthalten: "\\Myserver\root\default". Den Namen des Computers kann auch einen DNS-Namen oder die IP-Adresse sein. Die `ConnectServerWmi` Funktion kann auch eine Verbindung herstellen mit IPv6-Computern mit einer IPv6-Adresse.

`strUser` eine leere Zeichenfolge darf nicht sein. Wenn in die Domäne angegeben ist `strAuthority`, er darf nicht auch enthalten sein `strUser`, oder die Funktion gibt `WBEM_E_INVALID_PARAMETER`.


## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
