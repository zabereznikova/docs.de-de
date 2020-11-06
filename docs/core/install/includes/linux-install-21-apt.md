---
ms.openlocfilehash: 188fef66444cd60f59a3cb9619c0d86efd155f99
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93136113"
---

### <a name="install-the-sdk"></a>Installieren des SDKs

Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core. Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-sdk-2.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).

### <a name="install-the-runtime"></a>Installieren der Runtime

Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten. Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die Runtime für .NET Core mit der höchsten Kompatibilität. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket aspnetcore-runtime-2.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung für APT](#apt-troubleshooting).

Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie dazu im vorangegangenen Befehl `aspnetcore-runtime-2.1` durch `dotnet-runtime-2.1`.

```bash
sudo apt-get install -y dotnet-runtime-2.1
```
