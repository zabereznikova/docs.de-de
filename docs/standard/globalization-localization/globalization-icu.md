---
title: Globalisierung und ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET Framework], about globalization
- global applications, globalization
- international applications [.NET Framework], globalization
- world-ready applications, globalization
- application development [.NET Framework], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: 60533fbb215ffe8baba7e2d200faa1c4937294b9
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654880"
---
# <a name="net-globalization-and-icu"></a>.NET-Globalisierung und ICU

In der Vergangenheit verwendeten die .NET-Globalisierungs-APIs verschiedene zugrunde liegende Bibliotheken auf verschiedenen Plattformen. Unter UNIX haben die APIs [International Components for Unicode (ICU)](http://site.icu-project.org/home) und unter Windows [National Language Support (NLS)](/windows/win32/intl/national-language-support) verwendet. Dies führte zu einigen Verhaltensunterschieden in einigen Globalisierungs-APIs, wenn Anwendungen auf verschiedenen Plattformen ausgeführt wurden. Verhaltensunterschiede waren in den folgenden Bereichen ersichtlich:

- Kulturen und Kulturdaten
- Groß-/Kleinschreibung von Zeichenfolgen
- Sortieren und Suchen von Zeichenfolgen
- Sortieren von Schlüsseln
- Zeichenfolgennormalisierung
- Unterstützung für internationalisierte Domänennamen (IDN)
- Anzeigename der Zeitzone unter Linux

Ab .NET 5.0 haben Entwickler mehr Kontrolle darüber, welche zugrunde liegende Bibliothek verwendet wird. So können in Anwendungen plattformübergreifende Unterschiede vermieden werden.

## <a name="icu-on-windows"></a>ICU unter Windows

Das Windows 10-Update von Mai 2019 und höhere Versionen enthalten [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) als Teil des Betriebssystems, und .NET 5.0 und höhere Versionen verwenden standardmäßig ICU. Wenn die Ausführung unter Windows erfolgt, versuchen .NET 5.0 und höhere Versionen, `icu.dll` zu laden. Wenn die DLL verfügbar ist, wird sie für die Globalisierungsimplementierung verwendet.  Wenn diese Bibliothek nicht gefunden oder geladen werden kann, z. B. bei Ausführung mit älteren Versionen von Windows, greifen .NET 5.0 und höhere Versionen auf die NLS-basierte Implementierung zurück.

> [!NOTE]
> Selbst bei Verwendung von ICU verwenden die `CurrentCulture`-, `CurrentUICulture`- und `CurrentRegion`-Member weiterhin Windows-Betriebssystem-APIs, um Benutzereinstellungen zu berücksichtigen.

### <a name="using-nls-instead-of-icu"></a>Verwenden von NLS anstelle von ICU

Die Verwendung von ICU anstelle von NLS kann zu Verhaltensunterschieden bei einigen globalisierungsbezogenen Vorgängen führen. Um wieder NLS zu verwenden, kann ein Entwickler die ICU-Implementierung deaktivieren. Anwendungen können den NLS-Modus auf eine der folgenden Arten aktivieren:

- In der Projektdatei:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
</ItemGroup>
```

- In der Datei `runtimeconfig.json`:

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.UseNls": true
      }
  }
}
```

- Durch Festlegen der Umgebungsvariablen `DOTNET_SYSTEM_GLOBALIZATION_USENLS` auf den Wert `true` oder `1`.

> [!NOTE]
> Ein im Projekt oder in der Datei `runtimeconfig.json` festgelegter Wert hat Vorrang vor der Umgebungsvariablen.

Weitere Informationen finden Sie unter [Laufzeitkonfigurationseinstellungen](../../core/run-time-config/globalization.md#nls).

## <a name="app-local-icu"></a>App-lokale ICU

Jedes Release von ICU kann Fehlerbehebungen sowie aktualisierte CLDR-Daten (Common Locale Data Repository) enthalten, die die Sprachen der Welt beschreiben. Der Wechsel zwischen ICU-Versionen kann das Verhalten von Apps subtil beeinflussen, wenn es um globalisierungsbezogene Vorgänge geht.  Damit Anwendungsentwickler Konsistenz über alle Bereitstellungen hinweg sicherstellen können, ermöglichen .NET 5.0 und höhere Versionen Apps unter Windows und UNIX das Einbinden und Verwenden ihrer eigenen Kopie von ICU.

Anwendungen können einen App-lokalen ICU-Implementierungsmodus auf eine der folgenden Arten aktivieren:

- In der Projektdatei:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
</ItemGroup>
```

- In der Datei `runtimeconfig.json`:

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
      }
  }
}
```

- Durch Festlegen der Umgebungsvariablen `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` auf den Wert `<suffix>:<version>` oder `<version>`.

`<suffix>`: Optionales Suffix mit weniger als 36 Zeichen gemäß den öffentlichen ICU-Paketkonventionen. Wenn Sie eine benutzerdefinierte ICU-Bibliothek erstellt haben, können Sie diese so anpassen, dass die Bibliotheksnamen und exportierten Symbolnamen mit einem Suffix erstellt werden, z. B. `libicuucmyapp`, wobei `myapp` das Suffix ist.

`<version>`: Eine gültige ICU-Version, z. B. 67.1. Diese Version wird zum Laden der Binärdateien und zum Abrufen der exportierten Symbole verwendet.

Wenn Sie ICU laden möchten, wenn der App-lokale Switch festgelegt ist, verwendet .NET die <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType>-Methode, die mehrere Pfade überprüft. Die Methode versucht zuerst, die Bibliothek in der `NATIVE_DLL_SEARCH_DIRECTORIES`-Eigenschaft zu finden, die vom dotnet-Host basierend auf der Datei `deps.json` für die App erstellt wird. Weitere Informationen finden Sie unter [Standardüberprüfung](../../core/dependency-loading/default-probing.md).

Für eigenständige Apps sind keine besonderen Aktionen durch den Benutzer erforderlich. Es muss nur sichergestellt werden, dass sich die ICU-Bibliothek im App-Verzeichnis befindet (für eigenständige Apps ist das Arbeitsverzeichnis standardmäßig `NATIVE_DLL_SEARCH_DIRECTORIES`).

Wenn Sie ICU mithilfe eines NuGet-Pakets nutzen, funktioniert dies in frameworkabhängigen Anwendungen. NuGet löst die nativen Ressourcen auf und bindet sie in die Datei `deps.json` sowie in das Ausgabeverzeichnis für die Anwendung im Verzeichnis `runtimes`. .NET lädt Sie von dort.

Für frameworkabhängige Apps (nicht eigenständig), in denen ICU aus einem lokalen Build genutzt wird, müssen Sie zusätzliche Schritte ausführen. Das .NET SDK verfügt noch nicht über eine Funktion, die „lose“ native Binärdateien in `deps.json` integriert (weitere Informationen dazu finden Sie in [diesem SDK-Problem](https://github.com/dotnet/sdk/issues/11373)). Stattdessen können Sie dies aktivieren, indem Sie der Projektdatei der Anwendung zusätzliche Informationen hinzufügen. Zum Beispiel:

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

Dies muss für alle ICU-Binärdateien für die unterstützten Laufzeiten durchgeführt werden. Außerdem müssen die `NuGetPackageId`-Metadaten in der `RuntimeTargetsCopyLocalItems`-Elementgruppe mit einem NuGet-Paket übereinstimmen, auf das das Projekt tatsächlich verweist.

### <a name="macos-behavior"></a>macOS-Verhalten

`macOS` weist ein anderes Verhalten zum Auflösen abhängiger dynamischer Bibliotheken aus den in der `match-o`-Datei angegebenen Ladebefehlen als das Linux-Lademodul auf. Im Linux-Lademodul kann .NET versuchen, `libicudata`, `libicuuc` und `libicui18n` (in dieser Reihenfolge) zu verwenden, um das ICU-Abhängigkeitsdiagramm zu erfüllen. Unter macOS funktioniert dies jedoch nicht. Wenn Sie ICU unter macOS erstellen, erhalten Sie standardmäßig eine dynamische Bibliothek mit diesen Ladebefehlen in `libicuuc`. Beispiel:

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

Diese Befehle verweisen nur auf den Namen der abhängigen Bibliotheken für die anderen Komponenten von ICU. Das Lademodul führt die Suche nach den `dlopen`-Konventionen durch, wobei diese Bibliotheken in den Systemverzeichnissen enthalten sind oder die `LD_LIBRARY_PATH`-Umgebungsvariablen festgelegt werden oder sich ICU im Verzeichnis auf App-Ebene befindet. Wenn Sie `LD_LIBRARY_PATH` nicht festlegen oder sicherstellen können, dass sich die ICU-Binärdateien im Verzeichnis auf App-Ebene befinden, müssen Sie zusätzliche Schritte ausführen.

Es gibt einige Direktiven für das Ladeprogramm (z. B. `@loader_path`), die das Ladeprogramm anweisen, diese Abhängigkeit im gleichen Verzeichnis wie die Binärdatei mit diesem Ladebefehl zu suchen. Es gibt zwei Möglichkeiten, dies zu erreichen:

- `install_name_tool -change`

  Führen Sie die folgenden Befehle aus:

```bash
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
```

- Patchen von ICU zum Generieren der Installationsnamen mit `@loader_path`

  Ändern Sie vor dem Ausführen der automatischen Konfiguration (`./runConfigureICU`) [diese Zeilen](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) wie folgt:

```
LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
```

## <a name="icu-on-webassembly"></a>ICU für WebAssembly

Eine Version von ICU ist verfügbar, die speziell für WebAssembly-Workloads gilt. Diese Version bietet Globalisierungskompatibilität mit Desktopprofilen. Um die ICU-Datendateigröße von 24 MB auf 1,4 MB zu reduzieren (oder etwa 0,3 MB bei Komprimierung mit Brotli), weist diese Workload einige Einschränkungen auf.

Folgende APIs werden nicht unterstützt:

- <xref:System.Globalization.CultureInfo.EnglishName?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.NativeName?displayProperty=nameWithType>
- <xref:System.Globalization.DateTimeFormatInfo.NativeCalendarName?displayProperty=nameWithType>
- <xref:System.Globalization.RegionInfo.NativeName?displayProperty=nameWithType>

Die folgenden APIs werden mit Einschränkungen unterstützt:

- <xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> und <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> unterstützen die selten verwendeten <xref:System.Text.NormalizationForm.FormKC>- und <xref:System.Text.NormalizationForm.FormKD>-Formulare nicht.
- <xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> gibt denselben Wert zurück wie <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.

Außerdem finden Sie eine Liste der unterstützten Gebietsschemas im [dotnet/icu-Repository](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).
