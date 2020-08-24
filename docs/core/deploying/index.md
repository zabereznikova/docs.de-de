---
title: Anwendungsveröffentlichung
description: Erfahren Sie mehr über die Möglichkeiten zum Veröffentlichen einer .NET Core-Anwendung. Mit .NET Core können plattformspezifische oder plattformübergreifende Apps veröffentlicht werden. Sie können eine App als eigenständige oder frameworkabhängige App veröffentlichen. Der Modus wirkt sich darauf aus, wie ein Benutzer Ihre App ausführt.
ms.date: 04/01/2020
ms.openlocfilehash: ece5e46162fd4a8de0b996ba239e89cceca4dbca
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720110"
---
# <a name="net-core-application-publishing-overview"></a>Übersicht über die .NET Core-Anwendungsveröffentlichung

Mit .NET Core erstellte Anwendungen können in zwei verschiedenen Modi veröffentlicht werden, und der gewählte Modus beeinflusst, wie ein Benutzer Ihre App ausführt.

Die Veröffentlichung als *eigenständige* App erzeugt eine Anwendung, die die .NET Core-Runtime und die Bibliotheken, Ihre Anwendung und zugehörige Abhängigkeiten enthält. Benutzer der Anwendung können diese auf einem Computer ausführen, auf dem die .NET Core-Runtime nicht installiert ist.

Die Veröffentlichung als *frameworkabhängige* App erzeugt eine Anwendung, die nur die Anwendung selbst und die zugehörigen Abhängigkeiten umfasst. Benutzer der Anwendung müssen die .NET Core-Runtime separat installieren.

Beide Veröffentlichungsmodi erzeugen standardmäßig eine plattformspezifische ausführbare Datei. Frameworkabhängige Anwendungen können ohne ausführbare Datei erstellt werden, und sie sind plattformübergreifend.

Wenn eine ausführbare Datei erstellt wird, können Sie die Zielplattform mit einem Runtime-Bezeichner (RID) angeben. Weitere Informationen zu RIDs finden Sie im [.NET Core-RID-Katalog](../rid-catalog.md).

Die folgende Tabelle bietet einen Überblick über die Befehle, die zum Veröffentlichen einer App als frameworkabhängige oder eigenständige App verwendet werden, gruppiert nach SDK-Version:

| Typ                                                                                     | SDK 2.1 | SDK 3.x | Befehl |
| ---------------------------------------------------------------------------------------  | ------- | ------- | ------- |
| [Frameworkabhängige ausführbare Datei](#publish-framework-dependent) für die aktuelle Plattform |         | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [Frameworkabhängige ausführbare Datei](#publish-framework-dependent) für eine bestimmte Plattform  |         | ✔️      | [`dotnet publish -r <RID> --self-contained false`](../tools/dotnet-publish.md) |
| [Frameworkabhängige, plattformübergreifende Binärdatei](#publish-framework-dependent)               | ✔️      | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [Eigenständige ausführbare Datei](#publish-self-contained)                                    | ✔️      | ✔️      | [`dotnet publish -r <RID>`](../tools/dotnet-publish.md) |

Weitere Informationen finden Sie im Artikel zum [.NET Core-Befehl „dotnet publish“](../tools/dotnet-publish.md).

## <a name="produce-an-executable"></a>Erstellen einer ausführbaren Datei

Ausführbare Dateien sind nicht plattformübergreifend. Sie sind spezifisch für ein Betriebssystem und eine CPU-Architektur. Wenn Sie Ihre App veröffentlichen und eine ausführbare Datei erstellen, können Sie die App als [eigenständige](#publish-self-contained) oder [frameworkabhängige](#publish-framework-dependent) App veröffentlichen. Eine eigenständige App umfasst bei Veröffentlichung die .NET Core-Runtime gemeinsam mit der App, und Benutzer der App müssen sich keine Gedanken über die Installation von .NET Core machen, bevor sie die App ausführen. Als frameworkabhängige Apps veröffentlichte Apps enthalten weder die .NET Core-Runtime noch die zugehörigen Bibliotheken, sondern nur die App- und Drittanbieterabhängigkeiten.

Mit den folgenden Befehlen wird eine ausführbare Datei erstellt:

| Typ                                                                                     | SDK 2.1 | SDK 3.x | Befehl |
| ---------------------------------------------------------------------------------------- | ------- | ------- | ------- |
| [Frameworkabhängige ausführbare Datei](#publish-framework-dependent) für die aktuelle Plattform |         | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [Frameworkabhängige ausführbare Datei](#publish-framework-dependent) für eine bestimmte Plattform  |         | ✔️      | [`dotnet publish -r <RID> --self-contained false`](../tools/dotnet-publish.md) |
| [Eigenständige ausführbare Datei](#publish-self-contained)                                    | ✔️      | ✔️      | [`dotnet publish -r <RID>`](../tools/dotnet-publish.md) |

## <a name="produce-a-cross-platform-binary"></a>Erzeugen einer plattformübergreifenden Binärdatei

Beim Veröffentlichen Ihrer App als [frameworkabhängige](#publish-framework-dependent) App werden plattformübergreifende Binärdateien in Form von *DLL*-Dateien erstellt. Die *DLL*-Datei wird nach Ihrem Projekt benannt. Wenn Sie beispielsweise über eine App namens **word_reader** verfügen, wird eine Datei mit dem Namen *word_reader.dll* erstellt. Auf diese Weise veröffentlichte Apps werden mit dem Befehl `dotnet <filename.dll>` ausgeführt und können auf einer beliebigen Plattform verwendet werden.

Plattformübergreifende Binärdateien können auf beliebigen Betriebssystemen ausgeführt werden, sofern die anvisierte .NET Core-Runtime bereits installiert ist. Wenn die vorgesehene .NET Core-Runtime nicht installiert ist, kann die App möglicherweise mit einer neueren Runtime ausgeführt werden, wenn die App für ein Rollforward konfiguriert ist. Weitere Informationen finden Sie unter [Von Frameworks abhängige Apps führen einen Rollforward aus](../versions/selection.md#framework-dependent-apps-roll-forward).

Über die folgenden Befehle wird eine plattformübergreifende Binärdatei erzeugt:

| Typ                                                                                 | SDK 2.1 | SDK 3.x | Befehl |
| -----------------------------------------------------------------------------------  | ------- | ------- | ------- |
| [Frameworkabhängige, plattformübergreifende Binärdatei](#publish-framework-dependent)           | ✔️      | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |

## <a name="publish-framework-dependent"></a>Veröffentlichen als frameworkabhängige App

Apps, die als frameworkabhängig veröffentlicht werden, sind plattformübergreifend und enthalten die .NET Core-Runtime nicht. Die Benutzer Ihrer App müssen die .NET Core-Runtime installieren.

Beim Veröffentlichen einer frameworkabhängigen App werden eine [ plattformübergreifende Binärdatei](#produce-a-cross-platform-binary) als *DLL*-Datei und eine [ plattformspezifische ausführbare Datei](#produce-an-executable) speziell für Ihre aktuelle Plattform erzeugt. Die *DLL*-Datei ist plattformübergreifend, die ausführbare Datei hingegen nicht. Wenn Sie beispielsweise eine auf Windows ausgerichtete App namens **word_reader** veröffentlichen, werden die ausführbare Datei *word_reader.exe* und die Binärdatei *word_reader.dll* erstellt. Wenn Sie als Zielplattform Linux oder macOS verwenden, werden eine ausführbare *word_reader*-Datei und die Binärdatei *word_reader.dll* erstellt. Weitere Informationen zu RIDs finden Sie im [.NET Core-RID-Katalog](../rid-catalog.md).

> [!IMPORTANT]
> Das .NET Core SDK 2.1 erzeugt keine plattformspezifischen ausführbaren Dateien, wenn Sie eine frameworkabhängige App veröffentlichen.

Die plattformübergreifende Binärdatei Ihrer App kann mit dem Befehl `dotnet <filename.dll>` auf einer beliebigen Plattform ausgeführt werden. Wenn die App ein NuGet-Paket mit plattformspezifischen Implementierungen verwendet, werden alle Plattformabhängigkeiten gemeinsam mit der App in den Veröffentlichungsordner kopiert.

Sie können eine ausführbare Datei für eine bestimmte Plattform erstellen, indem Sie die `-r <RID> --self-contained false`-Parameter an den Befehl [`dotnet publish`](../tools/dotnet-publish.md) übergeben. Bei Auslassen des `-r`-Parameters wird eine ausführbare Datei für Ihre aktuelle Plattform erstellt. Alle NuGet-Pakete, die plattformspezifische Abhängigkeiten für die Zielplattform umfassen, werden in den Veröffentlichungsordner kopiert.

### <a name="advantages"></a>Vorteile

- **Kleine Bereitstellung**\
Nur Ihre App und die zugehörigen Abhängigkeiten werden verteilt. Die .NET Core-Runtime und die Bibliotheken werden vom Benutzer installiert, und alle Apps verwenden die Runtime gemeinsam.

- **Plattformübergreifend**\
Ihre App und eine beliebige .NET-basierte Bibliothek werden auf anderen Betriebssystemen ausgeführt. Sie müssen keine Zielplattform für Ihre App definieren. Weitere Informationen zum .NET-Dateiformat finden Sie unter [.NET-Assemblydateiformat](../../standard/assembly/file-format.md).

- **Verwendung der neuesten gepatchten Runtime**\
Die App verwendet die neueste Runtime (innerhalb der vorgesehenen Haupt-/Nebenversion der .NET Core-Familie), die auf dem Zielsystem installiert ist. Auf diese Weise kann Ihre App automatisch die neueste gepatchte Version der .NET Core-Runtime nutzen. Dieses Standardverhalten kann außer Kraft gesetzt werden. Weitere Informationen finden Sie unter [Von Frameworks abhängige Apps führen einen Rollforward aus](../versions/selection.md#framework-dependent-apps-roll-forward).

### <a name="disadvantages"></a>Nachteile

- **Vorinstallation der Runtime erforderlich**\
Ihre App kann nur ausgeführt werden, wenn die anvisierte .NET Core-Version bereits auf dem Hostsystem installiert ist. Sie können ein Rollforwardverhalten für die App konfigurieren, um entweder eine spezifische Version von .NET anzufordern oder eine neuere Version von .NET Core zuzulassen. Weitere Informationen finden Sie unter [Von Frameworks abhängige Apps führen einen Rollforward aus](../versions/selection.md#framework-dependent-apps-roll-forward).

- **Mögliche .NET Core-Änderungen**\
Es ist möglich, dass die .NET Core-Runtime und die Bibliotheken auf dem Computer aktualisiert werden, auf dem die App ausgeführt wird. In seltenen Fällen kann dies das Verhalten Ihrer App ändern, wenn Sie die .NET Core-Bibliotheken verwenden – was bei den meisten App der Fall ist. Sie können konfigurieren, wie Ihre App neuere Versionen von .NET Core verwendet. Weitere Informationen finden Sie unter [Von Frameworks abhängige Apps führen einen Rollforward aus](../versions/selection.md#framework-dependent-apps-roll-forward).

Die folgenden Nachteile gelten nur für das .NET Core 2.1 SDK.

- **Verwenden des Befehls `dotnet` zum Starten der App**\
Benutzer müssen den Befehl `dotnet <filename.dll>` verwenden, um Ihre App zu starten. Das .NET Core 2.1 SDK erzeugt keine plattformspezifischen ausführbaren Dateien für Apps, die als frameworkabhängige Apps veröffentlicht werden.

### <a name="examples"></a>Beispiele

Veröffentlichen einer plattformübergreifenden, frameworkabhängigen App. Für Ihre App werden eine ausführbare Datei für Ihre aktuelle Plattform sowie eine *DLL*-Datei erstellt.

```dotnet
dotnet publish
```

Veröffentlichen einer plattformübergreifenden, frameworkabhängigen App. Für die App werden eine ausführbare 64-Bit-Datei für Linux und eine *DLL*-Datei erstellt. Dieser Befehl funktioniert nicht mit dem .NET Core SDK 2.1.

```dotnet
dotnet publish -r linux-x64 --self-contained false
```

## <a name="publish-self-contained"></a>Veröffentlichung einer eigenständigen App

Durch die Veröffentlichung einer eigenständigen App wird eine plattformspezifische ausführbare Datei erzeugt. Der Ausgabeordner der Veröffentlichung enthält alle Komponenten der App – einschließlich .NET Core-Bibliotheken und Zielruntime. Die App ist von anderen .NET Core-Apps isoliert und verwendet keine lokal installierte, gemeinsam verwendete Runtime. Der Benutzer Ihrer App muss .NET Core nicht herunterladen und installieren.

Die ausführbare Binärdatei wird für die angegebene Zielplattform generiert. Wenn Sie beispielsweise über eine App namens **word_reader** verfügen und eine eigenständige ausführbare App für Windows veröffentlichen, wird die Datei *word_reader.exe* erstellt. Bei einer Veröffentlichung für Linux oder macOS wird eine *word_reader*-Datei erstellt. Die Zielplattform und -architektur wird mit dem `-r <RID>`-Parameter für den Befehl [`dotnet publish`](../tools/dotnet-publish.md) angegeben. Weitere Informationen zu RIDs finden Sie im [.NET Core-RID-Katalog](../rid-catalog.md).

Wenn die App plattformspezifische Abhängigkeiten aufweist, z. B. ein NuGet-Paket mit plattformspezifischen Abhängigkeiten, werden diese gemeinsam mit der App in den Veröffentlichungsordner kopiert.

### <a name="advantages"></a>Vorteile

- **Steuerung der .NET Core-Version**\
Sie steuern, welche Version von .NET Core mit Ihrer App bereitgestellt wird.

- **Plattformspezifische Zielfestlegung**\
Da Sie Ihre App für jede Plattform veröffentlichen müssen, kennen Sie die Ausführungsziele für Ihre App. Wenn .NET Core eine neue Plattform einführt, können die Benutzer Ihre App erst dann auf dieser Plattform ausführen, wenn Sie eine Version für diese Plattform veröffentlichen. Sie können Ihre App auf Kompatibilitätsprobleme testen, bevor die Benutzer Ihre App auf der neuen Plattform ausführen.

### <a name="disadvantages"></a>Nachteile

- **Größere Bereitstellungen**\
Da Ihre App die .NET Core-Runtime und sämtliche App-Abhängigkeiten enthält, sind die Downloadgröße und der benötigte Festplattenspeicher umfangreicher als bei einer [frameworkabhängigen](#publish-framework-dependent) Version.

  > [!TIP]
  > Sie können die Größe Ihrer Bereitstellung für Linux-Systeme um etwa 28 MB reduzieren, indem Sie den [*invarianten Globalisierungsmodus*](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md) von .NET Core verwenden. Hierdurch wird Ihre App gezwungen, alle Kulturen wie die [invariante Kultur](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType) zu behandeln.

  > [!TIP]
  > Mit dem [Kürzungsfeature](trim-self-contained.md) (Vorschauphase) können Sie die Größe Ihrer Bereitstellung weiter reduzieren.

- **Schwierigere Aktualisierung der .NET Core-Version**\
Die (mit Ihrer App verteilte) .NET Core-Runtime kann nur durch die Veröffentlichung einer neuen Version Ihrer App aktualisiert werden. Nach Bedarf aktualisiert .NET Core jedoch kritische Sicherheitspatches für die Frameworkbibliothek auf dem Computer, auf dem Ihre App ausgeführt wird. Sie sind für die gesamte Validierung dieses Sicherheitspatchszenarios verantwortlich.

### <a name="examples"></a>Beispiele

Veröffentlichung einer eigenständigen App. Es wird eine ausführbare 64-Bit-Datei für macOS erstellt.

```dotnet
dotnet publish -r osx-x64
```

Veröffentlichung einer eigenständigen App. Es wird eine ausführbare 64-Bit-Datei für Windows erstellt.

```dotnet
dotnet publish -r win-x64
```

## <a name="see-also"></a>Siehe auch

- [Bereitstellen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)
- [Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)
- [.NET Core-RID-Katalog (Runtime Identifier)](../rid-catalog.md)
- [Auswählen der zu verwendenden .NET Core-Version](../versions/selection.md)
