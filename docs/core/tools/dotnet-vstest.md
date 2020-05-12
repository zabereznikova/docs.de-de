---
title: Befehl „dotnet vstest“
description: Der dotnet vstest-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 02/27/2020
ms.openlocfilehash: f7db58f4aab59354b8c69ce0371324c23482dafe
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975393"
---
# <a name="dotnet-vstest"></a>dotnet vstest

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

> [!IMPORTANT]
> Der Befehl `dotnet vstest` wird von `dotnet test` abgelöst, der nun zum Ausführen von Assemblys verwendet werden kann. Weitere Informationen finden Sie unter [`dotnet test`](dotnet-test.md).

## <a name="name"></a>name

`dotnet-vstest`: Führt Tests auf Grundlage der angegebenen Assemblys aus.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a>Beschreibung

Der `dotnet-vstest`-Befehl führt die `VSTest.Console`-Befehlszeilenanwendung aus, um automatisierte Komponententests auszuführen.

## <a name="arguments"></a>Argumente

- **`TEST_FILE_NAMES`**

  Führt Tests auf Grundlage der angegebenen Assemblys aus. Trennt mehrere Test-Assemblynamen durch Leerzeichen. Platzhalter werden unterstützt.

## <a name="options"></a>Optionen

- **`--Blame`**

  Führt die Tests im blame-Modus aus. Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen. In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.

- **`--Diag <PATH_TO_LOG_FILE>`**

  Aktiviert die ausführlichen Protokolle für die Testplattform. Protokolle werden in die angegebene Datei geschrieben.

- **`--Framework <FRAMEWORK>`**

  .NET Framework-Zielversion, in der der Test ausgeführt wird. `.NETFramework,Version=v4.6` und `.NETCoreApp,Version=v1.0` sind Beispiele für gültige Werte. Andere unterstützte Werte sind `Framework40`, `Framework45`, `FrameworkCore10` und `FrameworkUap10`.

- **`--InIsolation`**

  Führt die Tests in einem isolierten Prozess aus. Dadurch ist die Wahrscheinlichkeit, dass der *vstest.console.exe*-Prozess bei Testfehlern beendet wird, weniger hoch, die Tests werden jedoch möglicherweise langsamer ausgeführt.

- **`-lt|--ListTests <FILE_NAME>`**

  Listet alle gefundenen Tests aus dem angegebenen Testcontainer auf.

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  Geben Sie eine Protokollierung für die Testergebnisse an.

  - Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter. Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen. Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  Mit dieser Option können Sie Tests parallel ausführen. Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung. Geben Sie eine explizite Anzahl von Kernen an, indem Sie die `MaxCpuCount`-Eigenschaft unter dem `RunConfiguration`-Knoten in der Datei *runsettings* festlegen.

- **`--ParentProcessId <PROCESS_ID>`**

  Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.

- **`--Platform <PLATFORM_TYPE>`**

  Verwendete Zielplattformarchitektur für die Testausführung. Gültige Werte sind `x86`, `x64` und `ARM`.

- **`--Port <PORT>`**

  Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.

- **`--ResultsDirectory:<PATH>`**

  Das Verzeichnis mit den Testergebnissen wird am angegebenen Pfad erstellt, falls es noch nicht vorhanden ist.

- **`--Settings <SETTINGS_FILE>`**

  Einstellungen, die beim Ausführen von Tests verwendet werden.

- **`--TestAdapterPath <PATH>`**

  Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.

- **`--TestCaseFilter <EXPRESSION>`**

  Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen. `<EXPRESSION>` hat das Format `<property>Operator<value>[|&<EXPRESSION>]`, wobei der Operator `=`, `!=`, oder `~` ist. Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`. Klammern `()` werden zum Gruppieren untergeordneter Ausdrücke verwendet. Weitere Informationen finden Sie unter [TestCase-Filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).

- **`--Tests <TEST_NAMES>`**

  Führt Tests aus, die mit den eingegebenen Werten übereinstimmen. Trennt mehrere Werte per Komma voneinander ab.

- **`-?|--Help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`@<file>`**

  Liest eine Antwortdatei für mehrere Optionen.

- **`args`**

  Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen. Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist. Trennt mehrere Argumente durch Leerzeichen.

## <a name="examples"></a>Beispiele

Mit dem folgenden Befehl werden Tests in *mytestproject.dll* ausgeführt:

```dotnetcli
dotnet vstest mytestproject.dll
```

Mit dem folgenden Befehl werden Tests in *mytestproject.dll* ausgeführt und in einen benutzerdefinierten Ordner mit benutzerdefiniertem Namen exportiert:

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

Mit dem folgenden Befehl werden Tests in *mytestproject.dll* und *myothertestproject.exe* ausgeführt:

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

Führt `TestMethod1`-Tests aus:

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

Führt `TestMethod1`- und `TestMethod2`-Tests aus:

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a>Siehe auch

- [Befehlszeilenoptionen für VSTest.Console.exe](/visualstudio/test/vstest-console-options)
