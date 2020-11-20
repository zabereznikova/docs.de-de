---
ms.openlocfilehash: 3932cf51b5194dba7956cd62ced3985a2e6311f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506805"
---

<!-- Note, this content is copied in ../macos.md. Any fixes should be applied there too, though content may be different -->

Als Alternative zu den Paket-Managern können Sie das SDK und die Runtime herunterladen und manuell installieren. Die manuelle Installation wird normalerweise im Rahmen von CI-Tests (Continuous Integration) oder unter nicht unterstützten Linux-Distributionen durchgeführt. Für Entwickler oder Benutzer eignet sich in der Regel die Verwendung eines Paket-Managers besser.

Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Laden Sie zunächst entweder für das SDK oder die Runtime eine **binäre** Version auf einer der folgenden Websites herunter:

- ✔️ [.NET 5.0-Downloads](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [.NET Core 3.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [.NET Core 2.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Alle .NET Core-Downloads](https://dotnet.microsoft.com/download/dotnet-core)

Extrahieren Sie als Nächstes die heruntergeladene Datei, und führen Sie den Befehl `export` aus, um von .NET verwendete Variablen festzulegen. Stellen Sie anschließend sicher, dass sich .NET in PATH befindet.

Laden Sie zunächst ein binäres .NET-Release herunter, um die Runtime zu extrahieren und die .NET-CLI-Befehle im Terminal bereitzustellen. Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle im Verzeichnis aus, in dem die Datei gespeichert wurde. Je nachdem, was Sie heruntergeladen haben, kann der Name der Archivdatei abweichen.

**Verwenden Sie den folgenden Befehl, um die Runtime zu extrahieren:**

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**Verwenden Sie den folgenden Befehl, um das SDK zu extrahieren:**

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Mit den oben aufgeführten `export`-Befehlen werden nur die .NET-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.
>
> Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen. Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen. Zum Beispiel:
>
> - **Bash-Shell**: *~/.bash_profile*, *~/.bashrc*
> - **Korn-Shell**: *~/.kshrc* oder *.profile*
> - **Z-Shell**: *~/.kshrc* oder *.profile*
>
> Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu. Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.
>
> Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.

Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.
