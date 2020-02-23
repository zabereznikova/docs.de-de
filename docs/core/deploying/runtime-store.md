---
title: Laufzeitpaketspeicher
description: Erfahren Sie, wie Sie den Laufzeitpaketspeicher für Manifeste nutzen, die von .NET Core verwendet werden.
ms.date: 08/12/2017
ms.openlocfilehash: 7a833ed95147608c6fb403f8f0dec179d2a73833
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448957"
---
# <a name="runtime-package-store"></a>Laufzeitpaketspeicher

Ab .NET Core 2.0 ist es möglich, Apps mit einer bekannten Reihe von Paketen, die in der Zielumgebung vorhanden sind, zu verpacken und bereitzustellen. Die Vorteile sind eine schnellere Bereitstellung, ein geringerer Speicherplatzverbrauch auf dem Datenträger und in manchen Fällen eine verbesserte Startleistung.

Dieses Feature wird als *Laufzeitpaketspeicher* implementiert. Dabei handelt es sich um ein Verzeichnis auf der Festplatte, in dem Pakete gespeichert werden (normalerweise unter */usr/local/share/dotnet/store* unter macOS/Linux und *C:/Programme/dotnet/store* unter Windows). In diesem Verzeichnis gibt es Unterverzeichnisse für Architekturen und [target frameworks (Zielframeworks)](../../standard/frameworks.md). Das Dateilayout ist ähnlich wie [NuGet assets are laid out on disk (die Anordnung von NuGet-Objekten auf der Festplatte)](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):

```
\dotnet
    \store
        \x64
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
        \x86
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
```

Die Pakete im Laufzeitpaketspeicher werden in einer *Zielmanifestdatei* aufgelistet. Entwickler können auf dieses Manifest abzielen, wenn sie ihre App veröffentlichen. Das Zielmanifest wird normalerweise vom Besitzer der als Ziel festgelegten Produktionsumgebung bereitgestellt.

## <a name="preparing-a-runtime-environment"></a>Vorbereiten einer Laufzeitumgebung

Der Administrator einer Laufzeitumgebung kann Apps für eine schnellere Bereitstellung und einen geringeren Speicherplatzverbrauch auf der Festplatte optimieren, indem er einen Laufzeitpaketspeicher und ein entsprechendes Zielmanifest erstellt.

Zuerst muss ein *Paketspeichermanifest* erstellt werden, das die Pakete auflistet, aus denen sich der Laufzeitpaketspeicher zusammensetzt. Dieses Dateiformat ist kompatibel mit dem Projektdateiformat (*csproj*).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

**Beispiel**

Das im folgenden Beispiel dargestellte Paketspeichermanifest (*packages.csproj*) wird verwendet, um [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) und [`Moq`](https://www.nuget.org/packages/moq/) zu einem Laufzeitpaketspeicher hinzuzufügen:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

Bereitstellen des Laufzeitpaketspeichers durch Ausführen von `dotnet store` mit dem Paketspeichermanifest, der Laufzeit und dem Framework:

```dotnetcli
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

**Beispiel**

```dotnetcli
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

Sie können mehrere Zielpfade von Paketspeichermanifesten an einen einzigen [`dotnet store`](../tools/dotnet-store.md)-Befehl übergeben, indem Sie die Option und den Pfad im Befehl wiederholen.

Standardmäßig ist die Ausgabe des Befehls ein Paketspeicher, der sich im Unterverzeichnis *.dotnet/store* des Benutzerprofils befindet. Sie können einen anderen Speicherort angeben, indem Sie die Option `--output <OUTPUT_DIRECTORY>` verwenden. Das Stammverzeichnis des Speichers enthält die Zielmanifestdatei *artifact.xml*. Diese Datei kann zum Download zur Verfügung gestellt und von App-Autoren verwendet werden, die diesen Speicher bei der Veröffentlichung anzielen möchten.

**Beispiel**

Die Datei *artifact.xml* wird erzeugt, nachdem das vorherige Beispiel ausgeführt wurde. Beachten Sie, dass es sich bei [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) um eine Abhängigkeit von `Moq` handelt, sodass dieses automatisch integriert und in der Manifestdatei *artifact.xml* angezeigt wird.

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a>Veröffentlichen einer App mit einem Zielmanifest

Wenn Sie eine Zielmanifestdatei auf Ihrer Festplatte haben, geben Sie den Pfad zu dieser Datei an, wenn Sie Ihre App mit dem [`dotnet publish`](../tools/dotnet-publish.md)-Befehl veröffentlichen:

```dotnetcli
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

**Beispiel**

```dotnetcli
dotnet publish --manifest manifest.xml
```

Sie stellen die resultierende veröffentlichte App für eine Umgebung bereit, die die im Zielmanifest beschriebenen Pakete enthält. Wenn dies nicht der Fall ist, führt das zu einem Startfehler der App.

Geben Sie mehrere Zielmanifeste an, wenn Sie eine App veröffentlichen, indem Sie die Option und den Pfad wiederholen (zum Beispiel `--manifest manifest1.xml --manifest manifest2.xml`). Wenn Sie dies tun, wird die App für die Vereinigungsmenge der Pakete zugeschnitten, die in den für den Befehl bereitgestellten Zielmanifestdateien angegeben werden.

## <a name="specifying-target-manifests-in-the-project-file"></a>Angeben von Zielmanifesten in der Projektdatei

Eine Alternative zum Angeben von Zielmanifesten mit dem [`dotnet publish`](../tools/dotnet-publish.md)-Befehl ist, diese in der Projektdatei als eine durch Semikolons getrennte Liste von Pfaden unter dem Tag **\<TargetManifestFiles>** anzugeben.

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

Geben Sie die Zielmanifeste nur in der Projektdatei an, wenn die Zielumgebung für die App bekannt ist, zum Beispiel bei .NET Core-Projekten. Für Open-Source-Projekte ist dies nicht der Fall. Die Benutzer von Open-Source-Projekten stellen diese üblicherweise für verschiedene Produktionsumgebungen bereit. Diese Produktionsumgebungen verfügen im Allgemeinen über verschiedene vorinstallierte Pakete. Sie können keine Annahmen über die Zielmanifeste in solchen Umgebungen machen, deshalb sollten Sie die Option `--manifest` von [`dotnet publish`](../tools/dotnet-publish.md) verwenden.

## <a name="aspnet-core-implicit-store"></a>Impliziter Speicher für ASP.NET Core

Der implizite Speicher für ASP.NET Core gilt nur für ASP.NET Core 2.0. Es wird dringend empfohlen, ASP.NET Core 2.1 und höher für Anwendungen zu verwenden, die den impliziten Speicher **nicht** verwenden. ASP.NET Core 2.1 und höher verwenden das freigegebene Framework.

Das Feature für den Laufzeitpaketspeicher wird implizit von einer ASP.NET Core-App verwendet, wenn die App als [Framework-abhängige Bereitstellung (FDD)](index.md#publish-runtime-dependent) bereitgestellt wird. Die Ziele in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) beinhalten Manifeste, die auf implizite Paketspeicher auf dem Zielsystem verweisen. Darüber hinaus resultiert jede FDD-App, die vom Paket `Microsoft.AspNetCore.All` abhängig ist, in einer veröffentlichten App, die nur die App und ihre Objekte enthält, nicht aber die Pakete, die im Metapaket `Microsoft.AspNetCore.All` aufgelistet sind. Es wird davon ausgegangen, dass diese Pakete auf dem Zielsystem vorhanden sind.

Der Laufzeitpaketspeicher wird bei der Installation des .NET Core SDK auf dem Host installiert. Andere Installationsprogramme stellen möglicherweise den Laufzeitpaketspeicher bereit, einschließlich der Zip-/Tarball-Installationen des .NET Core SDK, `apt-get`, Red Hat Yum, dem .NET Core Windows Server-Hostingpakets und manuellen Installationen des Laufzeitpaketspeichers.

Versichern Sie sich, dass das .NET Core SDK in der Zielumgebung installiert ist, wenn Sie eine App für [Framework-abhängige Bereitstellung (FDD)](index.md#publish-runtime-dependent) bereitstellen. Wenn die App für eine Umgebung bereitgestellt wird, die ASP.NET Core nicht enthält, können Sie den impliziten Speicher deaktivieren, indem Sie **\<PublishWithAspNetCoreTargetManifest>** angeben, das in der Projektdatei wie im folgenden Beispiel auf `false` festgelegt ist:

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE]
> Bei Apps für die [eigenständige Bereitstellung (SCD)](index.md#publish-self-contained) wird davon ausgegangen, dass das Zielsystem die erforderlichen Manifestpakete nicht unbedingt enthält. Deshalb kann **\<PublishWithAspNetCoreTargetManifest>** für eine SCD-App nicht auf `true` festgelegt werden.

Wenn Sie eine Anwendung bereitstellen, die von einem in der Bereitstellung vorhandenen Manifest abhängig ist (die Assembly ist im Ordner *bin* enthalten), wird der Laufzeitpaketspeicher für diese Assembly auf dem Host *nicht verwendet*. Die Assembly im Ordner *bin* wird unabhängig von ihrem Vorhandensein im Laufzeitpaketspeicher auf dem Host verwendet.

Die Version der Abhängigkeit, die im Manifest angegeben ist, muss mit der Version der Abhängigkeit im Laufzeitpaketspeicher übereinstimmen. Wenn ein Versionskonflikt zwischen der Abhängigkeit im Zielmanifest und der Version im Laufzeitpaketspeicher vorliegt, und die App in ihrer Bereitstellung nicht die erforderliche Version des Pakets enthält, führt dies zu einem Fehlstart der App. Die Ausnahme enthält den Namen des Zielmanifests, das die Assembly im Laufzeitpaketspeicher aufgerufen hat. Das hilft Ihnen bei der Behebung des Konflikts.

Wenn die Bereitstellung bei der Veröffentlichung *gekürzt* ist, werden nur die spezifischen Versionen der Manifestpakete, die Sie angeben, aus der veröffentlichten Ausgabe zurückbehalten. Die Pakete der angegebenen Versionen müssen auf dem Host vorhanden sein, damit die App starten kann.

## <a name="see-also"></a>Siehe auch

- [dotnet-publish](../tools/dotnet-publish.md)
- [dotnet-store](../tools/dotnet-store.md)
