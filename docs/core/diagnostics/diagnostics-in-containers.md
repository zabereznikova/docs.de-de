---
title: Sammeln von Diagnosen in Containern
description: In diesem Artikel erfahren Sie, wie Sie .NET Core-Diagnosetools in Docker-Containern verwenden können.
ms.date: 09/01/2020
ms.openlocfilehash: cf4bbdf75e943f093a2202f91303a2eea7125487
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916208"
---
# <a name="collect-diagnostics-in-containers"></a>Sammeln von Diagnosen in Containern

Die gleichen Diagnosetools, die für die Diagnose von .NET Core-Problemen in anderen Szenarien nützlich sind, funktionieren auch in Docker-Containern. Für einige Tools sind jedoch spezielle Schritte erforderlich, damit sie in einem Container funktionieren. In diesem Artikel wird beschrieben, wie Tools zum Sammeln von Leistungsüberwachungsdaten und Speicherabbildern in Docker-Containern verwendet werden können.

## <a name="using-net-core-cli-tools-in-a-container"></a>Verwenden von .NET Core-CLI-Tools in einem Container

**Diese Tools gelten für: ✔️** .NET Core 3.0 SDK und neuere Versionen

Die globalen .NET Core-CLI-Diagnosetools ([`dotnet-counters`](dotnet-counters.md), [`dotnet-dump`](dotnet-dump.md), [`dotnet-gcdump`](dotnet-gcdump.md) und [`dotnet-trace`](dotnet-trace.md)) sind so konzipiert, dass sie in einer Vielzahl von Umgebungen und somit direkt in Docker-Containern eingesetzt werden können. Aus diesem Grund stellen diese Tools die bevorzugte Methode dar, um in .NET Core-Szenarien für .NET Core 3.0 oder höher (bzw. 3.1 oder höher im Fall von `dotnet-gcdump`) Diagnoseinformationen in Containern zu sammeln.

Der einzige erschwerende Faktor bei der Verwendung dieser Tools in einem Container besteht darin, dass sie mit dem .NET Core SDK installiert werden und dass viele Docker-Container ohne das .NET Core SDK ausgeführt werden. Eine einfache Lösung für dieses Problem besteht darin, die Tools im anfänglichen Docker-Image zu installieren. Das .NET Core SDK muss für die Tools nicht ausgeführt, sondern nur installiert werden. Daher ist es möglich, ein Dockerfile mit einem [mehrstufigen Build](https://docs.docker.com/develop/develop-images/multistage-build/) zu erstellen, der die Tools in einer Buildstage installiert (in der das .NET Core SDK enthalten ist) und dann die Binärdateien in das endgültige Image kopiert. Der einzige Nachteil dieses Ansatzes besteht in der Größe des Docker-Images.

```dockerfile
# In build stage
# Install desired .NET CLI diagnostics tools
RUN dotnet tool install --tool-path /tools dotnet-trace
RUN dotnet tool install --tool-path /tools dotnet-counters
RUN dotnet tool install --tool-path /tools dotnet-dump

...

# In final stage
# Copy diagnostics tools
WORKDIR /tools
COPY --from=build /tools .
```

Alternativ dazu kann das .NET Core SDK bei Bedarf in einem Container installiert werden, um die CLI-Tools zu installieren. Beachten Sie, dass durch die Installation des .NET Core SDK als Nebeneffekt die .NET Core-Runtime neu installiert wird. Stellen Sie sicher, dass Sie die SDK-Version installieren, die der im Container vorliegenden Runtime entspricht.

### <a name="using-net-core-global-cli-tools-in-a-sidecar-container"></a>Verwenden globaler CLI-Tools von .NET Core in einem Sidecarcontainer

Wenn Sie die globalen CLI-Diagnosetools von .NET Core zur Diagnose von Prozessen in einem anderen Container verwenden möchten, müssen Sie die folgenden zusätzlichen Anforderungen beachten:

1. Die Container müssen einen [Prozessnamespace](https://docs.docker.com/engine/reference/run/#pid-settings---pid) freigeben (damit Tools im Sidecarcontainer auf Prozesse im Zielcontainer zugreifen können).
2. Die globalen CLI-Diagnosetools von .NET Core benötigen Zugriff auf Dateien, die von der .NET Core-Runtime in das Verzeichnis „/tmp“ geschrieben werden. Daher muss das Verzeichnis „/tmp“ über eine Volumebereitstellung von Ziel- und Sidecarcontainer gemeinsam genutzt werden. Dies lässt sich beispielsweise umsetzen, indem die Container ein [Volume](https://docs.docker.com/storage/volumes/#create-and-manage-volumes) oder ein Kubernetes-[emptyDir](https://kubernetes.io/docs/concepts/storage/volumes/#emptydir)-Volume gemeinsam verwenden. Wenn Sie versuchen, die Diagnosetools von einem Sidecarcontainer aus zu verwenden, ohne das Verzeichnis „/tmp“ freizugeben, erhalten Sie eine Fehlermeldung, dass der Prozess „keine kompatible .NET-Runtime ausführt“.

## <a name="using-perfcollect-in-a-container"></a>Verwenden von `PerfCollect` in einem Container

**Dieses Tool gilt für: ✔️** .NET Core 2.1 und neuere Versionen

Das [`PerfCollect`](./trace-perfcollect-lttng.md)-Skript ist für die Sammlung von Leistungsüberwachungsdaten nützlich und wird für die Erfassung von Überwachungsdaten vor .NET Core 3.0 empfohlen. Wenn Sie `PerfCollect` in einem Container verwenden, beachten Sie die folgenden Anforderungen:

1. Für `PerfCollect` ist die [`SYS_ADMIN`-Funktion](https://man7.org/linux/man-pages/man7/capabilities.7.html) (zur Ausführung des `perf`-Tools) erforderlich. Stellen Sie daher sicher, dass der Container [mit dieser Funktion gestartet wird](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities).
2. Für `PerfCollect` müssen einige Umgebungsvariablen vor dem Start der App festgelegt werden, für die ein Profil erstellt werden soll. Diese können entweder in einem [Dockerfile](https://docs.docker.com/engine/reference/builder/#env) oder beim [Starten des Containers](https://docs.docker.com/engine/reference/run/#env-environment-variables) festgelegt werden. Da diese Variablen in normalen Produktionsumgebungen nicht festgelegt werden sollten, ist es üblich, sie beim Starten eines Containers für die Profilerstellung hinzuzufügen. Folgende zwei Variablen sind für PerfCollect erforderlich:
    1. COMPlus_PerfMapEnabled=1
    1. COMPlus_EnableEventLog=1

### <a name="using-perfcollect-in-a-sidecar-container"></a>Verwenden von `PerfCollect` in einem Sidecarcontainer

Wenn Sie `PerfCollect` in einem Container ausführen möchten, um ein Profil für einen .NET Core-Prozess in einem anderen Container zu erstellen, ist die Vorgehensweise mit folgenden Ausnahmen nahezu identisch:

1. Die zuvor erwähnten Umgebungsvariablen („COMPlus_PerfMapEnabled“ und „COMPlus_EnableEventLog“) müssen für den Zielcontainer festgelegt werden (nicht für den, in dem `PerfCollect` ausgeführt wird).
2. Der Container, in dem `PerfCollect` ausgeführt wird, muss über die `SYS_ADMIN`-Funktion verfügen (nicht der Zielcontainer).
3. Die beiden Container müssen [einen Prozessnamespace gemeinsam verwenden](https://docs.docker.com/engine/reference/run/#pid-settings---pid).

## <a name="using-createdump-in-a-container"></a>Verwenden von `createdump` in einem Container

**Dieses Tool gilt für: ✔️** .NET Core 2.1 und neuere Versionen

Als Alternative zu `dotnet-dump` kann [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) zum Erstellen von Kernspeicherabbildern unter Linux verwendet werden, die sowohl native als auch verwaltete Informationen enthalten. Das Tool `createdump` wird mit der .NET Core-Runtime installiert und befindet sich bei libcoreclr.so (in der Regel unter „/usr/share/dotnet/shared/Microsoft.NETCore.App/[Version]“). Das Tool funktioniert in einem Container genauso wie in nicht in Containern ausgeführten Linux-Umgebungen. Die einzige Ausnahme besteht darin, dass das Tool die [`SYS_PTRACE`-Funktion](https://man7.org/linux/man-pages/man7/capabilities.7.html) erfordert und der Docker-Container daher [mit dieser Funktion gestartet werden muss](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities).

### <a name="using-createdump-in-a-sidecar-container"></a>Verwenden von `createdump` in einem Sidecarcontainer

Wenn Sie mit `createdump` ein Speicherabbild über einen Prozess in einem anderen Container erstellen möchten, ist die Vorgehensweise mit folgenden Ausnahmen nahezu identisch:

1. Der Container, in dem `createdump` ausgeführt wird, muss über die `SYS_PTRACE`-Funktion verfügen (nicht der Zielcontainer).
2. Die beiden Container müssen [einen Prozessnamespace gemeinsam verwenden](https://docs.docker.com/engine/reference/run/#pid-settings---pid).
