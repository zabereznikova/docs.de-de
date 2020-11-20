---
ms.openlocfilehash: cc394741e399f4fc54dd67f1736f7027badf4c7d
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507104"
---

### <a name="install-the-sdk"></a>Installieren des SDKs

Das .NET SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET. Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Führen Sie die folgenden Befehle aus, um das .NET SDK zu installieren:

```bash
sudo yum install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a>Installieren der Runtime

Die ASP.NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET erstellt wurden und die Runtime nicht enthalten. Durch die folgenden Befehle wird die ASP.NET Core-Runtime installiert, d. h. die Runtime für .NET mit der höchsten Kompatibilität. Führen Sie in Ihrem Terminal die folgenden Befehle aus:

```bash
sudo yum install aspnetcore-runtime-5.0
```

Als Alternative zur ASP.NET Core-Runtime können Sie die .NET-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet: Ersetzen Sie dazu im vorangegangenen Befehl `aspnetcore-runtime-5.0` durch `dotnet-runtime-5.0`:

```bash
sudo yum install dotnet-runtime-5.0
```
