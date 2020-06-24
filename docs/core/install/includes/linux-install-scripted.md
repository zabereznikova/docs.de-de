---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602717"
---

Die [dotnet-install-Skripts](../../tools/dotnet-install-script.md) werden für die Automatisierung und Installation des **SDK** ohne Administratorrechte verwendet. Sie können das Skript unter <https://dot.net/v1/dotnet-install.sh> herunterladen.

Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1. Um die aktuelle Version zu installieren, bei der es sich möglicherweise nicht um eine LTS-Version handelt, nutzen Sie den Parameter `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Um die .NET Core-Runtime anstelle des SDK zu installieren, geben Sie den Parameter `--runtime` an.

```bash
./dotnet-install.sh -c Current --runtime
```

Sie können eine bestimmte Version installieren, indem Sie mit dem Parameter `-c` die gewünschte Version angeben. Mit dem folgenden Befehl wird .NET Core SDK 3.1 installiert.

```bash
./dotnet-install.sh -c 3.1
```

Weitere Informationen finden Sie in der [ Referenz zu dotnet-install-Skripts](../../tools/dotnet-install-script.md).
