---
title: Installieren zusätzlicher ML.NET-Abhängigkeiten
description: In diesem Artikel erfahren Sie, wie Sie native Bibliotheken installieren, von denen ML.NET-Pakete abhängig sind, die jedoch nicht in der Installation von NuGet-Paketen enthalten sind.
ms.date: 04/02/2020
author: natke
ms.author: nakersha
ms.custom: how-to
ms.openlocfilehash: 0b870542706c065295d48205b7780e568e267ab6
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888275"
---
# <a name="install-extra-mlnet-dependencies"></a>Installieren zusätzlicher ML.NET-Abhängigkeiten

In den meisten Fällen ist die Installation von ML.NET auf allen Betriebssystem einfach, da lediglich die entsprechenden NuGet-Pakete referenziert werden müssen.

```bash
dotnet add package Microsoft.ML
```

In den manchen Fällen gibt es zusätzliche jedoch Installationsanforderungen, insbesondere, wenn native Komponenten erforderlich sind. In dieser Dokumentation werden die Installationsanforderungen für solche Fälle beschrieben. Die Abschnitte sind nach den jeweiligen `Microsoft.ML.*`-NuGet-Paketen unterteilt, die die zusätzliche Abhängigkeit enthalten.

## <a name="microsoftmltimeseries-microsoftmlautoml"></a>Microsoft.ML.TimeSeries und Microsoft.ML.AutoML

Beide dieser Pakete verfügen über eine Abhängigkeit vom Paket `Microsoft.ML.MKL.Redist`, das wiederum eine Abhängigkeit von `libiomp` aufweist.

### <a name="windows"></a>Windows

Es sind keine weiteren Installationsschritte erforderlich. Die Bibliothek wird installiert, wenn das NuGet-Paket zu einem Projekt hinzugefügt wird.

### <a name="linux"></a>Linux

1. Installieren Sie den GPG-Schlüssel für das Repository.

    ```bash
    sudo bash
    # <type your user password when prompted.  this will put you in a root shell>
    # cd to /tmp where this shell has write permission
    cd /tmp
    # now get the key:
    wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now install that key
    apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now remove the public key file exit the root shell
    rm GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    exit
    ```

2. Fügen Sie das APT-Repository für MKL hinzu.

    ```bash
    sudo sh -c 'echo deb https://apt.repos.intel.com/mkl all main > /etc/apt/sources.list.d/intel-mkl.list'
    ```

3. Aktualisieren von Paketen

    ```bash
    sudo apt-get update
    ```

4. Installieren Sie MKL.

    ```bash
    sudo apt-get install <COMPONENT>-<VERSION>.<UPDATE>-<BUILD_NUMBER>
    ```

    Zum Beispiel:

    ```bash
    sudo apt-get install intel-mkl-64bit-2020.0-088
    ```

    Ermitteln Sie den Speicherort von `libiomp.so`.

    ```bash
    find /opt -name "libiomp5.so"
    ```

    Zum Beispiel:

    ```output
    /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin/libiomp5.so
    ```

5. Fügen Sie diesen Speicherort zum Pfad zum Laden der Bibliothek hinzu:

    ```bash
    sudo ldconfig /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_li
    ```

### <a name="mac"></a>Mac

1. Installieren Sie die Bibliothek mit `Homebrew`.

    ```bash
    brew update && brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f5b1ac99a7fba27c19cee0bc4f036775c889b359/Formula/libomp.rb && brew link libomp --force
    ```
