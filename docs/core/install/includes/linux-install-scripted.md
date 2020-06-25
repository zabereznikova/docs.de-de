---
ms.openlocfilehash: fb78e1439a680a8dbb9fc0eb8afdeee3efef7ead
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768395"
---

Die [dotnet-install-Skripts](../../tools/dotnet-install-script.md) werden für die Automatisierung sowie für Installationen von **SDK** und **Runtime** durch Benutzer ohne Administratorrechte verwendet. Sie können das Skript unter <https://dot.net/v1/dotnet-install.sh> herunterladen.

Das Skript installiert standardmäßig die neueste [LTS](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)-SDK-Version (Long-Term Support), die derzeit .NET Core 3.1 entspricht. Um die aktuelle Version zu installieren, bei der es sich möglicherweise nicht um eine LTS-Version handelt, nutzen Sie den Parameter `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Um die .NET Core-Runtime anstelle des SDK zu installieren, geben Sie den Parameter `--runtime` an.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Sie können eine bestimmte Version installieren, indem Sie mit dem Parameter `-c` die gewünschte Version angeben. Mit dem folgenden Befehl wird .NET Core SDK 3.1 installiert.

```bash
./dotnet-install.sh -c 3.1
```

Weitere Informationen finden Sie in der [ Referenz zu dotnet-install-Skripts](../../tools/dotnet-install-script.md).
