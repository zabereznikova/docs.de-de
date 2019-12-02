---
title: Runtimekonfiguration
description: Hier erfahren Sie, wie Sie .NET Core-Anwendungen mithilfe von Runtimekonfigurationseinstellungen konfigurieren.
ms.date: 11/13/2019
ms.openlocfilehash: e3922f6df81198b5e122f16d5cfc4b6d15cbb4ae
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567389"
---
# <a name="net-core-run-time-configuration-settings"></a>Konfigurationseinstellungen für die .NET Core-Runtime

.NET Core unterstützt die Verwendung von Konfigurationsdateien und Umgebungsvariablen, um das Verhalten von .NET Core-Anwendungen zur Laufzeit zu konfigurieren. Runtimekonfigurationen sind eine geeignete Option, wenn

- Sie den Quellcode für eine Anwendung nicht besitzen oder steuern und ihn deshalb nicht programmgesteuert konfigurieren können.

- mehrere Instanzen Ihrer Anwendung zur gleichen Zeit auf einem einzelnen System ausgeführt werden und Sie jede Instanz für die optimale Leistung konfigurieren möchten.

> [!NOTE]
> Diese Dokumentation ist in Bearbeitung. Wenn Sie bemerken, dass die Informationen in diesem Artikel entweder unvollständig oder falsch sind, [öffnen Sie ein Issue](https://github.com/dotnet/docs/issues), um uns darüber zu informieren, oder [reichen Sie einen Pull Request ein](https://github.com/dotnet/docs/pulls), um das Problem zu beheben. Weitere Informationen zum Einreichen von Pull Requests für das dotnet/docs-Repository finden Sie im [Leitfaden für Mitwirkende](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).

.NET Core bietet die folgenden Mechanismen zum Konfigurieren von Anwendungen zur Laufzeit:

- die [runtimeconfig.json](#runtimeconfigjson)-Datei

- [Umgebungsvariablen](#environment-variables)

Die Artikel in diesem Teil der Dokumentation sind nach Kategorie geordnet, z. B. Debuggen und Garbage Collection. Verfügbare Konfigurationsoptionen werden für *runtimeconfig.json* (nur .NET Core), *app.config* (nur .NET Framework) und Umgebungsvariablen angezeigt.

## <a name="runtimeconfigjson"></a>runtimeconfig.json

Geben Sie die Konfigurationsoptionen für die Runtime im Abschnitt **configproperties** der *runtimeconfig.json*-Datei an. Dieser Abschnitt hat das folgende Format:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

Hier ist ein Beispiel für eine Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

Die Datei *runtimeconfig.json* wird automatisch vom [dotnet build](../tools/dotnet-build.md)-Befehl im Buildverzeichnis erstellt. Sie wird auch erstellt, wenn Sie die Menüoption **Erstellen** in Visual Studio auswählen. Sie können die Datei bearbeiten, wenn sie erstellt wurde.

Einige Konfigurationswerte können auch programmgesteuert festgelegt werden, indem die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufgerufen wird.

## <a name="environment-variables"></a>Umgebungsvariablen

Umgebungsvariablen können verwendet werden, um einige Informationen zur Runtimekonfiguration bereitzustellen. Konfigurationseinstellungen, die als Umgebungsvariablen angegeben werden, verfügen generell über das Präfix **COMPlus_** .

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
