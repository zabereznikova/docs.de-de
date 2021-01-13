---
title: Konfigurieren eines Proxyservers bei Verwendung des Azure SDK für .NET
description: Verwenden einer HTTP[S]_PROXY-Umgebungsvariablen zum Definieren eines Proxys für das Azure SDK für .NET
ms.date: 12/10/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.openlocfilehash: 64d525f8a6c277a5ac383dfded828f2fd3cfd744
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700903"
---
# <a name="configure-a-proxy-server-when-using-the-azure-sdk-for-net"></a>Konfigurieren eines Proxyservers bei Verwendung des Azure SDK für .NET

Wenn Ihre Organisation für den Zugriff auf Internetressourcen die Verwendung eines Proxyservers verlangt, müssen Sie eine Umgebungsvariable mit Informationen zum Proxyserver festlegen, damit Sie das Azure SDK für .NET verwenden können.  

## <a name="configuration-using-environment-variables"></a>Konfigurieren mithilfe von Umgebungsvariablen

Je nachdem, ob Ihr Proxyserver HTTP oder HTTPS verwendet, müssen Sie entweder die Umgebungsvariable `HTTP_PROXY` oder die Umgebungsvariable `HTTPS_PROXY` festlegen. Die URL des Proxyservers hat das Format `http[s]://[username:password@]<ip_address_or_hostname>:<port>/`, wobei die Kombination `username:password` optional ist. Wenden Sie sich an den Netzwerkadministrator, um diesen um die IP-Adresse oder den Hostnamen, den Port und die Anmeldeinformationen für den Proxyserver zu bitten.

In den folgenden Beispielen wird gezeigt, wie Sie die entsprechenden Umgebungsvariablen in Befehlsshell- (Windows) und Bashumgebungen (Linux/Mac) festlegen können.  Nachdem Sie die passende Umgebungsvariable festgelegt haben, verwendet das Azure SDK für .NET den Proxyserver zur Laufzeit.

### <a name="cmd"></a>[cmd](#tab/cmd)

```cmd
rem Non-authenticated HTTP server:
set HTTP_PROXY=http://10.10.1.10:1180

rem Authenticated HTTP server:
set HTTP_PROXY=http://username:password@10.10.1.10:1180

rem Non-authenticated HTTPS server:
set HTTPS_PROXY=http://10.10.1.10:1180

rem Authenticated HTTPS server:
set HTTPS_PROXY=http://username:password@10.10.1.10:1180
```

### <a name="bash"></a>[Bash](#tab/bash)

```bash
# Non-authenticated HTTP server:
HTTP_PROXY=http://10.10.1.10:1180

# Authenticated HTTP server:
HTTP_PROXY=http://username:password@10.10.1.10:1180

# Non-authenticated HTTPS server:
HTTPS_PROXY=http://10.10.1.10:1180

# Authenticated HTTPS server:
HTTPS_PROXY=http://username:password@10.10.1.10:1180
```

---
