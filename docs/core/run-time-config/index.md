---
title: Runtimekonfigurationsoptionen
description: Hier erfahren Sie, wie Sie .NET Core-Anwendungen mithilfe von Runtimekonfigurationseinstellungen konfigurieren.
ms.date: 01/21/2020
ms.openlocfilehash: 21673a221d0f21202febf4730b955da66132d5f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538197"
---
# <a name="net-core-run-time-configuration-settings"></a>Konfigurationseinstellungen für die .NET Core-Runtime

.NET Core unterstützt die Verwendung von Konfigurationsdateien und Umgebungsvariablen, um das Verhalten von .NET Core-Anwendungen zur Laufzeit zu konfigurieren. Runtimekonfigurationen sind eine geeignete Option, wenn

- Sie den Quellcode für eine Anwendung nicht besitzen oder steuern und ihn deshalb nicht programmgesteuert konfigurieren können.

- mehrere Instanzen Ihrer Anwendung zur gleichen Zeit auf einem einzelnen System ausgeführt werden und Sie jede Instanz für die optimale Leistung konfigurieren möchten.

> [!NOTE]
> Diese Dokumentation ist in Bearbeitung. Wenn Sie bemerken, dass die Informationen in diesem Artikel entweder unvollständig oder falsch sind, [öffnen Sie ein Issue](https://github.com/dotnet/docs/issues), um uns darüber zu informieren, oder [reichen Sie einen Pull Request ein](https://github.com/dotnet/docs/pulls), um das Problem zu beheben. Weitere Informationen zum Einreichen von Pull Requests für das dotnet/docs-Repository finden Sie im [Leitfaden für Mitwirkende](/contribute/dotnet/dotnet-contribute).

.NET Core bietet die folgenden Mechanismen zum Konfigurieren des Anwendungsverhaltens zur Laufzeit:

- die [runtimeconfig.json](#runtimeconfigjson)-Datei

- [MSBuild-Eigenschaften](#msbuild-properties)

- [Umgebungsvariablen](#environment-variables)

> [!TIP]
> Wenn Sie eine Laufzeitoption mithilfe einer Umgebungsvariablen konfigurieren, wird diese Einstellung auf alle .NET Core-Apps angewendet. Wenn Sie eine Laufzeitoption in der Datei *runtimeconfig.json* oder in der Projektdatei konfigurieren, wird die Einstellung nur auf diese Anwendung angewendet.

Einige Konfigurationswerte können auch programmgesteuert festgelegt werden, indem die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufgerufen wird.

Die Artikel in diesem Teil der Dokumentation sind nach Kategorie geordnet, z. B. [Debuggen](debugging-profiling.md) und [Garbage Collection](garbage-collector.md). Gegebenenfalls werden Konfigurationsoptionen für *runtimeconfig.json*-Dateien, MSBuild-Eigenschaften, Umgebungsvariablen und, als Querverweis, *app.config*-Dateien für .NET Framework-Projekte angezeigt.

## <a name="runtimeconfigjson"></a>runtimeconfig.json

Wenn ein Projekt [erstellt](../tools/dotnet-build.md) wird, wird im Ausgabeverzeichnis eine Datei namens *[App-Name].runtimeconfig.json* generiert. Wenn eine *runtimeconfig.template.json*-Datei im selben Ordner liegt wie eine Projektdatei, werden alle in ihr enthaltenen Konfigurationsoptionen in der Datei *[App-Name].runtimeconfig.json* zusammengeführt. Wenn Sie die App selbst erstellen, legen Sie alle Konfigurationsoptionen in der Datei *runtimeconfig.template.json* fest. Wenn Sie die App nur ausführen, fügen Sie sie direkt in die Datei *[App-Name].runtimeconfig.json* ein.

> [!NOTE]
> Die Datei *[App-Name].runtimeconfig.json* wird bei nachfolgenden Builds überschrieben.

Geben Sie die Runtimekonfigurationsoptionen im Abschnitt **configProperties** der Datei *runtimeconfig.json* an. Dieser Abschnitt hat das folgende Format:

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a>Beispiel einer „[App-Name].runtimeconfig.jason“-Datei

Wenn Sie die Optionen in der JSON-Ausgabedatei angeben möchten, platzieren Sie sie unter der Eigenschaft `runtimeOptions`.

```json
{
  "runtimeOptions": {
    "tfm": "netcoreapp3.1",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "3.1.0"
    },
    "configProperties": {
      "System.GC.Concurrent": false,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

### <a name="example-runtimeconfigtemplatejson-file"></a>Beispiel einer „runtimeconfig.template.json“-Datei

Wenn Sie die Optionen in der template.json-Datei platzieren, lassen Sie die Eigenschaft `runtimeOptions` weg.

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a>MSBuild-Eigenschaften

Manche Runtimekonfigurationsoptionen können mithilfe von MSBuild-Eigenschaften in den Dateien *.csproj* oder *.vbproj* von .NET Core-Projekten im SDK-Stil festgelegt werden. MSBuild-Eigenschaften haben Vorrang vor Optionen, die in der Datei *runtimeconfig.template.json* festgelegt sind. Außerdem überschreiben sie alle Optionen, die Sie zur Buildzeit in der Datei *[App-Name].runtimeconfig.json* festgelegt haben.

Hier sehen Sie ein Beispiel für eine Projektdatei im SDK-Stil mit MSBuild-Eigenschaften zum Konfigurieren des Runtimeverhaltens:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
    <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

Die MSBuild-Eigenschaften zum Konfigurieren des Runtimeverhaltens finden Sie in den Artikeln für die einzelnen Bereiche, z. B. [Garbage Collection](garbage-collector.md). Sie werden auch im Abschnitt [Laufzeitkonfiguration](../project-sdk/msbuild-props.md#run-time-configuration-properties) der Referenz zu MSBuild-Eigenschaften für SDK-Projekte aufgeführt.

## <a name="environment-variables"></a>Umgebungsvariablen

Umgebungsvariablen können verwendet werden, um einige Informationen zur Runtimekonfiguration bereitzustellen. Wenn Sie eine Laufzeitoption mithilfe einer Umgebungsvariablen konfigurieren, wird diese Einstellung auf alle .NET Core-Apps angewendet. Konfigurationseinstellungen, die als Umgebungsvariablen angegeben werden, verfügen generell über das Präfix **COMPlus_** .

Sie können Umgebungsvariablen über die Windows-Systemsteuerung, die Befehlszeile oder programmgesteuert durch Aufruf der <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType>-Methode jeweils auf den Windows- und Linux-basierten Systemen definieren.

In den folgenden Beispielen wird dargestellt, wie eine Umgebungsvariable in der Befehlszeile festgelegt wird:

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
