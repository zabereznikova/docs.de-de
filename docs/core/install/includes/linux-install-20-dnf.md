---
ms.openlocfilehash: 787b0a04c5bf312ad3f3e7834664e70dae9678e0
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135996"
---

### <a name="install-the-sdk"></a>Installieren des SDKs

Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core. Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:

```bash
sudo dnf install dotnet-sdk-2.0
```

### <a name="install-the-runtime"></a>Installieren der Runtime

Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten. Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, die am besten kompatible Runtime für .NET Core. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo dnf install aspnetcore-runtime-2.0
```

Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie im vorangegangenen Befehl `aspnetcore-runtime-2.0` durch `dotnet-runtime-2.0`.

```bash
sudo dnf install dotnet-runtime-2.0
```
