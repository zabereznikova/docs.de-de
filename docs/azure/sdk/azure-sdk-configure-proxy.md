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
# <a name="configure-a-proxy-server-when-using-the-azure-sdk-for-net"></a><span data-ttu-id="5cdaa-103">Konfigurieren eines Proxyservers bei Verwendung des Azure SDK für .NET</span><span class="sxs-lookup"><span data-stu-id="5cdaa-103">Configure a proxy server when using the Azure SDK for .NET</span></span>

<span data-ttu-id="5cdaa-104">Wenn Ihre Organisation für den Zugriff auf Internetressourcen die Verwendung eines Proxyservers verlangt, müssen Sie eine Umgebungsvariable mit Informationen zum Proxyserver festlegen, damit Sie das Azure SDK für .NET verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5cdaa-104">If your organization requires the use of a proxy server to access internet resources, you will need to set an environment variable with the proxy server information to use the Azure SDK for .NET.</span></span>  

## <a name="configuration-using-environment-variables"></a><span data-ttu-id="5cdaa-105">Konfigurieren mithilfe von Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="5cdaa-105">Configuration using environment variables</span></span>

<span data-ttu-id="5cdaa-106">Je nachdem, ob Ihr Proxyserver HTTP oder HTTPS verwendet, müssen Sie entweder die Umgebungsvariable `HTTP_PROXY` oder die Umgebungsvariable `HTTPS_PROXY` festlegen.</span><span class="sxs-lookup"><span data-stu-id="5cdaa-106">Depending on if your proxy server uses HTTP or HTTPS, you will set either the environment variable `HTTP_PROXY` or `HTTPS_PROXY` respectively.</span></span> <span data-ttu-id="5cdaa-107">Die URL des Proxyservers hat das Format `http[s]://[username:password@]<ip_address_or_hostname>:<port>/`, wobei die Kombination `username:password` optional ist.</span><span class="sxs-lookup"><span data-stu-id="5cdaa-107">The proxy server URL has the form `http[s]://[username:password@]<ip_address_or_hostname>:<port>/` where the `username:password` combination is optional.</span></span> <span data-ttu-id="5cdaa-108">Wenden Sie sich an den Netzwerkadministrator, um diesen um die IP-Adresse oder den Hostnamen, den Port und die Anmeldeinformationen für den Proxyserver zu bitten.</span><span class="sxs-lookup"><span data-stu-id="5cdaa-108">To get the IP address or hostname, port and credentials for your proxy server, consult your network administrator.</span></span>

<span data-ttu-id="5cdaa-109">In den folgenden Beispielen wird gezeigt, wie Sie die entsprechenden Umgebungsvariablen in Befehlsshell- (Windows) und Bashumgebungen (Linux/Mac) festlegen können.</span><span class="sxs-lookup"><span data-stu-id="5cdaa-109">The following examples show how to set the appropriate environment variables in command shell (Windows) and bash (Linux/Mac) environments.</span></span>  <span data-ttu-id="5cdaa-110">Nachdem Sie die passende Umgebungsvariable festgelegt haben, verwendet das Azure SDK für .NET den Proxyserver zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="5cdaa-110">Setting the appropriate environment variable will then cause the Azure SDK for .NET to use the proxy server at runtime.</span></span>

### <a name="cmd"></a>[<span data-ttu-id="5cdaa-111">cmd</span><span class="sxs-lookup"><span data-stu-id="5cdaa-111">cmd</span></span>](#tab/cmd)

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

### <a name="bash"></a>[<span data-ttu-id="5cdaa-112">Bash</span><span class="sxs-lookup"><span data-stu-id="5cdaa-112">bash</span></span>](#tab/bash)

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
