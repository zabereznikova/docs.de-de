---
ms.openlocfilehash: 36f1ee26def82d426b6637ae96f382fc89791a2f
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135848"
---

### <a name="install-the-sdk"></a>Installieren des SDKs

Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core. Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren.

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a>Installieren der Runtime

Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten. Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die am besten kompatible Runtime für .NET Core. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie im vorangegangenen Befehl `aspnetcore-runtime-2.1` durch `dotnet-runtime-3.1`.

```bash
sudo zypper install dotnet-runtime-3.1
```
