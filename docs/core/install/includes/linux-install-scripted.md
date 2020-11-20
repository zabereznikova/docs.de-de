---
ms.openlocfilehash: 07dd58c314c826c426193b829ea1f64669fb888b
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594571"
---

Die [dotnet-install-Skripts](../../tools/dotnet-install-script.md) werden für die Automatisierung sowie für Installationen von **SDK** und **Runtime** durch Benutzer ohne Administratorrechte verwendet. Sie können das Skript unter <https://dot.net/v1/dotnet-install.sh> herunterladen.

Das Skript installiert standardmäßig die neueste [LTS](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)-SDK-Version (Long-Term Support), die derzeit .NET 3.1 entspricht. Um die aktuelle Version zu installieren, bei der es sich möglicherweise nicht um eine LTS-Version handelt, nutzen Sie den Parameter `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Geben Sie den Parameter `--runtime` an, um die .NET-Runtime anstelle des SDK zu installieren.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Sie können eine bestimmte Version installieren, indem Sie mit dem Parameter `-c` die gewünschte Version angeben. Mit dem folgenden Befehl wird .NET SDK 5.0 installiert.

```bash
./dotnet-install.sh -c 5.0
```

Weitere Informationen finden Sie in der [ Referenz zu dotnet-install-Skripts](../../tools/dotnet-install-script.md).
