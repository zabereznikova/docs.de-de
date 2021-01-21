---
title: Deinstallationstool
description: Eine Übersicht über das .NET Core-Deinstallationstool, ein Tool mit Anleitungen, das die kontrollierte Bereinigung von .NET Core SDKs und -Runtimes ermöglicht.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: ed43b4ec8437ae0ccaf5f1234758dda9f16bd51e
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235351"
---
# <a name="net-core-uninstall-tool"></a>.NET Core-Deinstallationstool

Mit dem [.NET Core-Deinstallationstool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) können Sie .NET Core SDKs und -Runtimes von einem System entfernen. Hierfür stehen Ihnen verschiedene Optionen zur Verfügung, mit denen Sie angeben können, welche Versionen deinstalliert werden sollen.

Das Tool unterstützt Windows und macOS. Linux wird aktuell nicht unterstützt.

Unter Windows kann das Tool nur SDKs und Runtimes deinstallieren, die mit einem der folgenden Installationsprogramme installiert wurden:

- .NET Core SDK- und -Runtime-Installer.
- Visual Studio-Installer in früheren Versionen als Visual Studio 2019, Version 16.3.

Unter macOS kann das Tool nur SDKs und Runtimes deinstallieren, die sich im Ordner */usr/local/share/dotnet* befinden.

Aufgrund dieser Einschränkungen ist das Tool möglicherweise nicht in der Lage, alle .NET Core SDKs und -Runtimes auf Ihrem Computer zu deinstallieren. Mit dem Befehl `dotnet --info` können Sie alle installierten .NET Core SDKs und -Runtimes ermitteln, einschließlich der SDKs und Runtimes, die dieses Tool nicht entfernen kann. Der Befehl `dotnet-core-uninstall list` zeigt an, welche SDKs mit dem Tool deinstalliert werden können. Ab Version 1.2 und höher können SDKs und Runtimes mit Version 5.0 und früher deinstalliert werden. Auf früheren Versionen des Tools können SDKs und Runtimes mit Version 3.1 und früher deinstalliert werden.

## <a name="install-the-tool"></a>Installieren des Tools

Sie können das .NET Core-Tool für die Deinstallation auf der [Seite mit den Versionen des Tools](https://aka.ms/dotnet-core-uninstall-tool) herunterladen und den Quellcode im GitHub-Repository [dotnet/cli-lab](https://github.com/dotnet/cli-lab) finden.

> [!NOTE]
> Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren. Daher sollte es in einem Verzeichnis mit schreibgeschütztem Zugriff installiert werden, z. B. in *C:\Programme* unter Windows oder in */usr/local/bin* unter macOS. Weitere Informationen finden Sie unter [Erhöhte Zugriffsrechte für dotnet-Befehle](../tools/elevated-access.md). Weitere Informationen finden Sie unter [Ausführliche Installationsanweisungen](https://aka.ms/dotnet-core-uninstall-tool).

## <a name="run-the-tool"></a>Ausführen des Tools

Die folgenden Schritte zeigen die empfohlene Vorgehensweise zum Ausführen des Deinstallationstools:

- [Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes](#step-1---display-installed-net-core-sdks-and-runtimes)
- [Schritt 2: Ausführen eines Testlaufs](#step-2---do-a-dry-run)
- [Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes](#step-3---uninstall-net-core-sdks-and-runtimes)
- [Schritt 4: Löschen des NuGet-Fallbackordners (optional)](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a>Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes

Der Befehl `dotnet-core-uninstall list` listet die installierten .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können. Einige SDKs und Runtimes werden möglicherweise von Visual Studio benötigt, und es wird ein Hinweis angezeigt, warum es nicht empfohlen wird, diese zu deinstallieren.

> [!NOTE]
> Die Ausgabe des `dotnet-core-uninstall list`-Befehls stimmt in den meisten Fällen nicht mit der Liste der installierten Versionen in der Ausgabe von `dotnet --info` überein. Insbesondere zeigt dieses Tool keine Versionen an, die über ZIP-Dateien installiert oder von Visual Studio verwaltet werden (alle Versionen, die mit Visual Studio 2019 16.3 oder höher installiert wurden). Eine Möglichkeit zur Überprüfung, ob eine Version von Visual Studio verwaltet wird, besteht darin, sie in `Add or Remove Programs` anzuzeigen. Hier werden in Visual Studio verwaltete Versionen in ihren Anzeigenamen als solche gekennzeichnet.

**dotnet-core-uninstall list**

#### <a name="synopsis"></a>Übersicht

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a>Optionen

## <a name="windows"></a>[Windows](#tab/windows)

* **`--aspnet-runtime`**

  Listet alle ASP.NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.

* **`--hosting-bundle`**

  Listet alle .NET Core-Hostingpakete auf, die mit diesem Tool deinstalliert werden können.

* **`--runtime`**

  Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.

* **`--sdk`**

  Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.

* **`-v, --verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `normal`.

* **`--x64`**

  Listet alle x64-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.

* **`--x86`**

  Listet alle x86-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--runtime`**

  Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.

* **`--sdk`**

  Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.

* **`-v, --verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `normal`.
  
---

#### <a name="examples"></a>Beispiele

* Listet alle .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können:

  ```console
  dotnet-core-uninstall list
  ```

* Listet alle  x64-.NET Core SDKs und -Runtimes auf:

  ```console
  dotnet-core-uninstall list --x64
  ```

* Listet aller x86-.NET Core SDKs auf:

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a>Schritt 2: Ausführen eines Testlaufs

Die Befehle `dotnet-core-uninstall dry-run` und `dotnet-core-uninstall whatif` zeigen die .NET Core SDKs und -Runtimes an, die auf der Grundlage der bereitgestellten Optionen ohne Ausführung der Deinstallation entfernt werden. Diese Befehle sind Synonyme.

**dotnet-core-uninstall dry-run und dotnet-core-uninstall whatif**

#### <a name="synopsis"></a>Übersicht

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a>Argumente

* **`VERSION`**

  Die angegebene Version, die deinstalliert werden soll. Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten. Antwortdateien werden ebenfalls unterstützt.

  > [!TIP]
  > Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.
  > Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.
  > Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.

#### <a name="options"></a>Optionen

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  Entfernt alle .NET Core SDKs und -Runtimes.

* **`--all-below <VERSION>[ <VERSION>...]`**

  Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist. Die angegebene Version bleibt installiert.

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.

* **`--all-but-latest`**

  Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.

* **`--all-lower-patches`**

  Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden. Diese Option schützt „global.json“.

* **`--all-previews`**

  Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.

* **`--all-previews-but-latest`**

  Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.

* **`--aspnet-runtime`**

  Entfernt nur ASP.NET Core-Runtimes.

* **`--hosting-bundle`**

  Entfernt nur .NET Core-Runtime- und -Hostingpakete.

* **`--major-minor <MAJOR_MINOR>`**

  Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.

* **`--runtime`**

  Entfernt nur .NET Core-Runtimes.

* **`--sdk`**

  Entfernt nur .NET Core SDKs.

* **`-v, --verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `normal`.

* **`--x64`**

  Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.

* **`--x86`**

  Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.

* **`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.

Notizen:

1. Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.
3. Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--all`**

  Entfernt alle .NET Core SDKs und -Runtimes.

* **`--all-below <VERSION>[ <VERSION>...]`**

  Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version. Die angegebene Version verbleibt auf dem Computer.

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.

* **`--all-but-latest`**

  Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.

* **`--all-lower-patches`**

  Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden. Diese Option schützt „global.json“.

* **`--all-previews`**

  Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.

* **`--all-previews-but-latest`**

  Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.

* **`--major-minor <MAJOR_MINOR>`**

  Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.

* **`--runtime`**

  Entfernt nur .NET Core-Runtimes.

* **`--sdk`**

  Entfernt nur .NET Core SDKs.

* **`-v, --verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `normal`.
  
* **`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.

Notizen:

1. Genau ein Element `--sdk` und `--runtime` ist erforderlich.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.

---

#### <a name="examples"></a>Beispiele

> [!NOTE]
> Standardmäßig sind .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, nicht in der Ausgabe von `dotnet-core-uninstall dry-run` enthalten. In den folgenden Beispielen sind einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers möglicherweise nicht in der Ausgabe enthalten. Wenn Sie alle SDKs und Runtimes einbeziehen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.

* Testlauf zum Entfernen aller .NET Core-Runtimes, die durch höhere Patches abgelöst wurden:

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* Testlauf zum Entfernen aller .NET Core SDKs mit einer kleineren Version als `2.2.301`:

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a>Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes

`dotnet-core-uninstall remove` deinstalliert .NET Core SDKs und -Runtimes, die durch eine Sammlung von Optionen angegeben werden. Ab Version 1.2 und höher können SDKs und Runtimes mit Version 5.0 und früher deinstalliert werden. Auf früheren Versionen des Tools können SDKs und Runtimes mit Version 3.1 und früher deinstalliert werden.

Da dieses Tool ein destruktives Verhalten aufweist, wird **unbedingt** empfohlen, vor dem Ausführen des Entfernungsbefehls einen Testlauf auszuführen. Der Testlauf zeigt Ihnen, welche .NET Core SDKs und -Runtimes entfernt werden, wenn Sie den Befehl `remove` verwenden. Lesen Sie [Sollte ich eine Version entfernen?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version), um zu erfahren, welche SDKs und Runtimes sicher entfernt werden können.

> [!CAUTION]
> Beachten Sie die folgenden Vorbehalte:
>
>- Dieses Tool kann Versionen des .NET Core SDK deinstallieren, die von `global.json`-Dateien auf Ihrem Computer benötigt werden. Sie können .NET Core SDKs über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.
>- Dieses Tool kann Versionen der .NET Core-Runtime deinstallieren, die von frameworkabhängigen Anwendungen auf Ihrem Computer benötigt werden. Sie können .NET Core-Runtimes über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.
>- Dieses Tool kann Versionen des .NET Core SDK und der -Runtime deinstallieren, die von Visual Studio benötigt werden. Wenn Sie Ihre Visual Studio-Installation beschädigen, führen Sie „Reparieren“ im Visual Studio-Installer aus, um zu einem funktionsfähigen Zustand zurückzukehren.

Standardmäßig behalten alle Befehle die .NET Core SDKs und -Runtimes bei, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden. Diese SDKs und Runtimes können deinstalliert werden, indem sie explizit als Argumente aufgelistet werden oder indem die Option `--force` verwendet wird.

Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren. Führen Sie das Tool in einer Administratoreingabeaufforderung unter Windows und mit `sudo` unter macOS aus. Die Befehle `dry-run` und `whatif` erfordern keine Erhöhung der Rechte.

**dotnet-core-uninstall remove**

#### <a name="synopsis"></a>Übersicht

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a>Argumente

* **`VERSION`**

  Die angegebene Version, die deinstalliert werden soll. Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten. Antwortdateien werden ebenfalls unterstützt.

  > [!TIP]
  > Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.
  > Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.
  > Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.

#### <a name="options"></a>Optionen

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  Entfernt alle .NET Core SDKs und -Runtimes.

* **`--all-below <VERSION>[ <VERSION>...]`**

  Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist. Die angegebene Version bleibt installiert.

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.

* **`--all-but-latest`**

  Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.

* **`--all-lower-patches`**

  Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden. Diese Option schützt „global.json“.

* **`--all-previews`**

  Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.

* **`--all-previews-but-latest`**

  Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.

* **`--aspnet-runtime`**

  Entfernt nur ASP.NET Core-Runtimes.

* **`--hosting-bundle`**

  Entfernt nur .NET Core-Hostingpakete

* **`--major-minor <MAJOR_MINOR>`**

  Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.

* **`--runtime`**

  Entfernt nur .NET Core-Runtimes.

* **`--sdk`**

  Entfernt nur .NET Core SDKs.

* **`-v, --verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `normal`.

* **`--x64`**

  Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.

* **`--x86`**

  Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.

* **`-y, --yes`** Führt den Befehl aus, ohne dass eine Bestätigung mit „Ja“ oder „Nein“ erforderlich ist.

* **`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.

Notizen:

1. Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.
3. Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--all`**

  Entfernt alle .NET Core SDKs und -Runtimes.

* **`--all-below <VERSION>[ <VERSION>...]`**

  Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version. Die angegebene Version verbleibt auf dem Computer.

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.

* **`--all-but-latest`**

  Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.

* **`--all-lower-patches`**

  Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden. Diese Option schützt „global.json“.

* **`--all-previews`**

  Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.

* **`--all-previews-but-latest`**

  Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.

* **`--major-minor <MAJOR_MINOR>`**

  Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.

* **`--runtime`**

  Entfernt nur .NET Core-Runtimes.

* **`--sdk`**

  Entfernt nur .NET Core SDKs.

* **`-v, --verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `normal`.

* **`-y, --yes`** Führt den Befehl aus, ohne dass eine J/N-Bestätigung erforderlich ist.
  
* **`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.

Notizen:

1. Genau ein Element `--sdk` und `--runtime` ist erforderlich.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.

---

#### <a name="examples"></a>Beispiele

> [!NOTE]
> Standardmäßig werden .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, beibehalten. In den folgenden Beispielen bleiben einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers ggf. erhalten. Wenn Sie alle SDKs und Runtimes entfernen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.

* Entfernen aller .NET Core-Runtimes mit Ausnahme der Version `3.0.0-preview6-27804-01`, ohne dass eine J/N-Bestätigung erforderlich ist:

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* Entfernen aller .NET Core 1.1 SDKs, ohne dass eine J/N-Bestätigung erforderlich ist:

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* Entfernen des .NET Core 1.1.11 SDK ohne Konsolenausgabe:

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* Entfernen aller .NET Core SDKs, die sicher von diesem Tool entfernt werden können:

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* Entfernen aller .NET Core SDKs, die von diesem Tool entfernt werden können, einschließlich der SDKs, die möglicherweise von Visual Studio benötigt werden (nicht empfohlen):

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* Entfernen aller .NET Core SDKs, die in der Antwortdatei `versions.rsp` angegeben sind

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  Der Inhalt von *versions.rsp* lautet wie folgt:
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a>Schritt 4: Löschen des NuGet-Fallbackordners (optional)

In einigen Fällen benötigen Sie `NuGetFallbackFolder` nicht mehr und möchten den Ordner ggf. löschen. Weitere Informationen zum Löschen dieses Ordners finden Sie unter [Entfernen des Ordners „NuGetFallbackFolder“](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).

## <a name="uninstall-the-tool"></a>Deinstallieren des Tools

## <a name="windows"></a>[Windows](#tab/windows)

1. Öffnen Sie **Software**.
2. Suchen Sie nach `Microsoft .NET Core SDK Uninstall Tool`.
3. Wählen Sie **Deinstallieren** aus.

## <a name="macos"></a>[macOS](#tab/macos)

Löschen Sie die heruntergeladene Datei *dotnet-core-uninstall.tar.gz* aus dem Verzeichnis, in dem sie installiert wurde. Wenn Sie den Inhalt dieser Datei in ein anderes Verzeichnis entzippt haben, stellen Sie sicher, dass Sie auch diesen Inhalt löschen.

---
