---
title: .NET Core Anwendungsbereitstellung
description: .NET Core Anwendungsbereitstellung
keywords: .NET, .NET Core, .NET Core Bereitstellung
author: rpetrusha
manager: wpickett
ms.date: 09/08/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: da7a31a0-8072-4f23-82aa-8a19184cb701
translationtype: Human Translation
ms.sourcegitcommit: 663f4102b82512e64ab39d8046c7298a7cf37de7
ms.openlocfilehash: 96eb2cc7ca948b3e372fa1363b1741624d791d27

---

# <a name="net-core-application-deployment"></a>.NET Core Anwendungsbereitstellung #

Sie können zwei Arten von Bereitstellungen für .NET Core-Anwendungen erstellen: 

- Framework-abhängige Bereitstellung. Wie der Name sagt, verwenden Framework-abhängige Bereitstellungen (FDD) eine gemeinsame systemweite Version von .NET Core, die auf dem Zielsystem vorhanden ist. Da .NET Core bereits vorhanden ist, ist Ihre Anwendung auch zwischen .NET Core-Installationen übertragbar. Ihre Anwendung enthält nur ihren eigenen Code und Drittanbieter-Abhängigkeiten, die außerhalb von .NET Core-Bibliotheken bestehen. FDDs enthalten DLL-Dateien, die mithilfe des [Dotnet-Hilfsprogramms](../tools/dotnet.md) über die Befehlszeile gestartet werden können. `dotnet app.dll` führt z.B. eine Anwendung namens `app` aus.

- Eigenständige Bereitstellung. Im Gegensatz zu FDD müssen bei einer eigenständigen Bereitstellung (SCD) die freigegebenen Komponenten nicht auf dem Zielsystem vorhanden sein. Alle Komponenten, einschließlich .NET Core-Bibliotheken und die .NET Core Runtime sind in der Anwendung enthalten und von anderen .NET Core-Anwendungen isoliert. SCDs enthalten eine ausführbare Datei (z.B. `app.exe` auf Windows-Plattformen für eine Anwendung namens `app`), die eine umbenannte Version des plattformspezifischen .NET Core-Host darstellt, und eine DLL-Datei (z.B. `app.dll`), die die eigentliche Anwendung ist.

## <a name="frameworkdependent-deployments-fdd"></a>Framework-abhängige Bereitstellungen (FDD) ##

Für eine FDD stellen Sie nur Ihre Anwendungen und Drittanbieter-Abhängigkeiten bereit. Sie müssen .NET Core nicht bereitstellen, da Ihre Anwendung die .NET Core- Version verwenden wird, die auf dem Zielsystem vorhanden ist. Dies ist das Standard-Bereitstellungsmodell für .NET Core-Anwendungen.

### <a name="why-create-a-frameworkdependent-deployment"></a>Warum eine Framework-abhängige Bereitstellung erstellen? ###

Die Bereitstellung einer FDD hat eine Reihe von Vorteilen:

- Sie müssen nicht im Voraus die Ziel-Betriebssysteme definieren, auf denen Ihre .NET Core-Anwendung ausgeführt wird. Da .NET Core unabhängig vom Betriebssystem ein gemeinsames PE-Dateiformat für ausführbare Dateien verwendet, kann .NET Core Ihrer Anwendung unabhängig vom zugrunde liegenden Betriebssystem ausführen. Weitere Informationen zum PE-Dateiformat finden Sie unter [.NET Assembly-Dateiformat](../../standard/assembly-format.md).

- Ihr Bereitstellungspaket ist klein. Sie müssen nur Ihre Anwendung und deren Abhängigkeiten und nicht .NET Core selbst bereitstellen.

- Mehrere Anwendungen verwenden die gleiche .NET Core-Installation, die Speicherplatz und Arbeitsspeicher auf dem Hostsystem verringert.

Es gibt auch einige Nachteile:

- Ihre Anwendung kann nur ausgeführt werden, wenn die .NET Core-Version die Sie anvisieren oder eine höhere Version bereits auf dem Hostsystem installiert ist.

- Es ist möglich, dass die .NET Core Runtime und die Bibliotheken ohne Ihr Wissen in zukünftigen Versionen geändert werden. In seltenen Fällen kann dies das Verhalten Ihrer Anwendung ändern.

### <a name="deploying-a-frameworkdependent-deployment"></a>Bereitstellen einer Framework-abhängigen Bereitstellung ###

Die Bereitstellung einer Framework-abhängigen Bereitstellung ohne Drittanbieter-Abhängigkeiten umfasst nur das Erstellen, Testen und Veröffentlichen der Anwendung. Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess. Das Beispiel nutzt das [Dotnet-Dienstprogramm](../tools/dotnet.md) über die Befehlszeile. Sie können allerdings auch eine Entwicklungsumgebung wie Visual Studio oder Visual Studio Code verwenden, um das Beispiel zu kompilieren, zu testen und zu veröffentlichen.

1. Erstellen Sie ein Verzeichnis für Ihr Projekt, und geben Sie über die Befehlszeile [dotnet new](../tools/dotnet-new.md) ein, um ein neues C#-Konsolenprojekt zu erstellen.

2. Öffnen Sie die `Program.cs`-Datei in einem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code. Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurde, werden angezeigt. Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.

    ```cs
    using System;
    using System.Text.RegularExpressions;

    namespace Applications.ConsoleApps
    {
        public class ConsoleParser
        {
            public static void Main()
            {
                 Console.WriteLine("Enter any text, followed by <Enter>:\n");
                 String s = Console.ReadLine();
                 ShowWords(s);
                 Console.Write("\nPress any key to continue... ");
                 Console.ReadKey();
          }

          private static void ShowWords(String s)
          {
              String pattern = @"\w+";
              var matches = Regex.Matches(s, pattern);
              if (matches.Count == 0)
                  Console.WriteLine("\nNo words were identified in your input.");
              else
              {
                  Console.WriteLine("\nThere are {0} words in your string:", matches.Count);
                  for (int ctr = 0; ctr < matches.Count; ctr++)
                      Console.WriteLine("   #{0,2}: '{1}' at position {2}", ctr,
                                        matches[ctr].Value, matches[ctr].Index);
              }
          }
      }
    }
    ```

3. Führen Sie den Befehl [dotnet restore](../tools/dotnet-restore.md) aus, um die im Projekt angegebenen Abhängigkeiten wiederherzustellen.

4. Erstellen Sie mithilfe des Befehls [Dotnet Build](../tools/dotnet-build.md) einen Debugbuild Ihrer Anwendung.

5. Nachdem Sie die Anwendung debuggt und getestet haben, können Sie mithilfe des `dotnet publish -f netcoreapp1.0 -c release`-Befehls die Dateien erstellen, die mit Ihrer Anwendung bereitgestellt werden. Dies erstellt eine Releaseversion (anstatt einer Debugversion) Ihrer Anwendung.

   Die resultierenden Dateien werden in ein Verzeichnis namens `publish` platziert, das sich in einem Unterverzeichnis des `.\bin\release\netcoreapp1.0`-Unterverzeichnis Ihres Projekts befindet.

6. Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält. Die Datei ist in erster Linie für das Debuggen von Ausnahmen zuständig. Sie können sich dafür entscheiden, sie nicht mit den Dateien Ihrer Anwendung zu verpacken.

Der vollständige Satz von Anwendungsdateien kann so bereitgestellt werden, wie Sie möchten. Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.

Das Installationsprogramm sollte zusätzlich zu den Binärdateien der Anwendung das freigegebene Framework-Installationsprogramm bündeln, oder als erforderliche Komponente im Rahmen der Anwendungsinstallation überprüfen.  Die Installation des gemeinsam genutzten Frameworks erfordert Administrator-/Root-Zugriff, da es sich um eine computerweite Installation handelt.

### <a name="deploying-a-frameworkdependent-deployment-with-thirdparty-dependencies"></a>Bereitstellen einer Framework-abhängigen Bereitstellung mit Drittanbieter-Abhängigkeiten ###

Das Bereitstellen einer Framework-abhängigen Bereitstellung mit einer oder mehreren Drittanbieter-Abhängigkeiten umfasst drei zusätzliche Schritte vor dem Ausführen des `dotnet restore`-Befehls:

1. Fügen Sie Verweise auf Drittanbieter-Bibliotheken zum `dependencies`-Teil Ihrer `project.json`-Datei hinzu. Der folgende `dependencies`-Abschnitt verwendet Json.NET als Drittanbieter-Bibliothek.

    ```json
    "dependencies": {
      "Microsoft.NETCore.App": {
        "type": "platform",
        "version": "1.0.0"
      },
      "Newtonsoft.Json": "9.0.1"
    },
    ```

2. Wenn noch nicht geschehen, laden Sie das NuGet-Paket mit der Drittanbieter-Abhängigkeit herunter. Um das Paket herunterzuladen, führen Sie nach dem Hinzufügen der Abhängigkeit den `dotnet restore`-Befehl aus. Da die Abhängigkeit zum Zeitpunkt der Veröffentlichung aus dem lokalen NuGet-Cache aufgelöst wurde, muss sie auf Ihrem System verfügbar sein.

Beachten Sie, dass eine Framework-abhängige Bereitstellung mit Drittanbieter-Abhängigkeiten nur so tragbar wie ihre Drittanbieter-Abhängigkeiten ist. Falls eine Drittanbieter-Bibliothek nur Mac OS unterstützen sollte, so wird die Anwendung nicht auf Windows-Systeme übertragbar sein. Dies kann geschehen, wenn die Drittanbieter-Abhängigkeit selbst vom nativen Code abhängt. Ein gutes Beispiel hierfür ist der Kestrel-Server. Wenn bei dieser Art von Drittanbieter-Abhängigkeit eine FDD für eine Anwendung erstellt wird, enthält die veröffentlichte Ausgabe einen Ordner für jede [Runtime-ID (RID)](../rid-catalog.md#what-are-rids), die die native Abhängigkeit unterstützt (und im NuGet-Paket vorhanden ist).

## <a name="selfcontained-deployments-scd"></a>Eigenständige Bereitstellungen (Self-contained deployments, SCD) ##

Bei einer eigenständigen Bereitstellung stellen Sie nicht nur Ihre Anwendung und jegliche Drittanbieter-Abhängigkeiten, sondern die .NET Core-Version, die Sie mit Ihrer Anwendung erstellen, bereit. Das Erstellen einer eigenständigen Bereitstellung schließt allerdings nicht die [nativen Abhängigkeiten von .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) selbst auf verschiedenen Plattformen mit ein (z.B. OpenSSL auf Mac OS). Diese müssen demnach vor dem Ausführen der Anwendung installiert werden. 

### <a name="why-deploy-a-selfcontained-deployment"></a>Warum eine eigenständige Bereitstellung? ###

Das Bereitstellen einer eigenständigen Bereitstellung hat zwei wesentliche Vorteile:

- Sie haben die alleinige Kontrolle über die .NET Core-Version, die mit Ihrer Anwendung bereitgestellt wird. .NET Core kann nur von Ihnen bearbeitet werden.

- Sie können sicher sein, dass das Zielsystem Ihre .NET Core-Anwendung ausführen kann, da Sie die .NET Core-Version bereitstellen, die darauf ausgeführt werden soll.

Es hat auch einige Nachteile:

- Da .NET Core in Ihrem Bereitstellungspaket enthalten ist, müssen Sie die Zielplattformen auswählen, für die Sie im Voraus Bereitstellungspaketen erstellen.

- Die Größe Ihres Bereitstellungspakets ist relativ groß, da es auch .NET Core, Ihre Anwendung und ihre Drittanbieter-Abhängigkeiten enthält.

- Das Bereitstellen von zahlreichen eigenständigen .NET Core-Anwendungen auf ein System kann viel Speicherplatz verbrauchen, da jede Anwendung .NET Core-Dateien dupliziert.

### <a name="a-namesimpleselfa-deploying-a-simple-selfcontained-deployment"></a> Bereitstellen einer einfachen eigenständigen Bereitstellung ###

Das Bereitstellen einer eigenständigen Bereitstellung ohne Drittanbieter-Abhängigkeiten umfasst das Erstellen des Projekts, das Ändern der Datei project.json, und das Erstellen, Testen und Veröffentlichen der Anwendung.  Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess. Das Beispiel nutzt das `dotnet`-Dienstprogramm von der Befehlszeile. Sie können allerdings auch eine Entwicklungsumgebung, wie z.B. Visual Studio oder Visual Studio Code verwenden, um das Beispiel zu kompilieren, testen und veröffentlichen.

1. Erstellen Sie ein Verzeichnis für Ihr Projekt, und geben Sie über die Befehlszeile `dotnet new` ein, um ein neues C#-Konsolenprojekt zu erstellen.

2. Öffnen Sie die `Program.cs`-Datei in einem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code. Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurde, werden angezeigt. Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.

    ```cs
    using System;
    using System.Text.RegularExpressions;

    namespace Applications.ConsoleApps
    {
        public class ConsoleParser
        {
            public static void Main()
            {
                 Console.WriteLine("Enter any text, followed by <Enter>:\n");
                 String s = Console.ReadLine();
                 ShowWords(s);
                 Console.Write("\nPress any key to continue... ");
                 Console.ReadKey();
          }

          private static void ShowWords(String s)
          {
              String pattern = @"\w+";
              var matches = Regex.Matches(s, pattern);
              if (matches.Count == 0)
                  Console.WriteLine("\nNo words were identified in your input.");
              else {
                  Console.WriteLine("\nThere are {0} words in your string:", matches.Count);
                  for (int ctr = 0; ctr < matches.Count; ctr++)
                      Console.WriteLine("   #{0,2}: '{1}' at position {2}", ctr,
                                        matches[ctr].Value, matches[ctr].Index);
              }
          }
      }
    }
    ```

3. Öffnen Sie die `project.json`-Datei, und entfernen Sie die folgende Zeile im `frameworks`-Abschnitt:

   ```json
   "type": "platform",
   ```
Der Framework-Abschnitt sollte wie folgt aussehen, nachdem Sie ihn geändert haben:

    ```json
    "frameworks": {
      "netcoreapp1.0": {
        "dependencies": {
          "Microsoft.NETCore.App": {
             "version": "1.0.0"
          }
        }
      }
    }
    ```
Das Entfernen des `"type": "platform"`-Attributs gibt an, dass das Framework als eine Reihe von für unsere Anwendung lokalen Komponenten, und nicht als ein systemweites Plattformpaket bereitgestellt wird.

4. Erstellen Sie einen `runtimes`-Abschnitt in Ihrer `project.json`-Datei, der die Plattformen Ihrer Zielanwendungen definiert, und die Runtime-ID für jede Zielplattform angibt. Sie finden eine RID-Liste im [RID-Katalog](../rid-catalog.md). Der folgende `runtimes`-Abschnitt gibt z.B. an, dass die Anwendung auf 64-Bit Windows 10-Betriebssystemen und der 64-Bit OS X-Version 10.10 ausgeführt wird.

    ```json
        "runtimes": {
          "win10-x64": {},
          "osx.10.10-x64": {}
        }
    ```
Beachten Sie, dass Sie auch ein Komma hinzufügen müssen, um den `runtimes`-Abschnitt vom vorherigen Abschnitt zu trennen.
Eine vollständige `project.json`-Beispieldatei wird später in diesem Abschnitt angezeigt.

6. Führen Sie den `dotnet restore`-Befehl aus, um die in Ihrem Projekt angegebenen Abhängigkeiten wiederherzustellen.

7. Erstellen Sie mithilfe des `dotnet build`-Befehls Debugversionen Ihrer Anwendung auf allen Zielplattformen. Wenn Sie den Runtime-ID, den Sie gerne erstellen würden, nicht angeben, erstellt der `dotnet build`-Befehl nur einen Build für die Runtime-ID des aktuellen Systems. Mit den folgenden Befehlen können Sie Ihre Anwendung für beide Zielplattformen erstellen:

    ```console
    dotnet build -r win10-x64
    dotnet build -r osx.10.10-x64
    ```
Die Debugbuilds Ihrer Anwendung für jede Plattform befinden sich im `.\bin\Debug\netcoreapp1.0\<runtime_identifier>`-Unterverzeichnis des Projekts.

8. Nachdem Sie die Anwendung debuggt und getestet haben, können Sie die Dateien, die mit Ihrer Anwendung für jede Plattform bereitgestellt werden, erstellen, indem Sie den `dotnet publish`-Befehl für beide Plattformen wie folgt nutzen:

   ```console
   dotnet publish -c release -r win10-x64
   dotnet publish -c release -r osx.10.10-x64
   ```
Dies erstellt eine Releaseversion (anstatt einer Debugversion) Ihrer Anwendung für jede Zielplattform. Die resultierenden Dateien werden in ein Unterverzeichnis namens `publish` platziert, das sich in einem Unterverzeichnis des `.\bin\release\netcoreapp1.0\<runtime_identifier>`-Unterverzeichnis Ihres Projekts befindet. Beachten Sie, dass jedes Unterverzeichnis den vollständigen Dateisatz enthält (Dateien Ihrer Anwendung und alle .NET Core-Dateien), der zum Starten Ihrer Anwendung erforderlich ist.

9. Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält. Die Datei ist in erster Linie für das Debuggen von Ausnahmen zuständig. Sie können sich dafür entscheiden, sie nicht mit den Dateien Ihrer Anwendung zu verpacken.

Die veröffentlichten Dateien können so bereitgestellt werden, wie Sie möchten. Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen. 

Nachfolgend ist die vollständige `project.json`-Datei für dieses Projekt angegeben.

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable",
    "emitEntryPoint": true
  },
  "dependencies": {},
  "frameworks": {
    "netcoreapp1.0": {
      "dependencies": {
        "Microsoft.NETCore.App": {
          "version": "1.0.0"
        }
      }
    }
  },
  "runtimes": {
    "win10-x64": {},
    "osx.10.10-x64": {}
  }
}
```

### <a name="deploying-a-selfcontained-deployment-with-thirdparty-dependencies"></a>Bereitstellen einer eigenständigen Bereitstellung mit Drittanbieter-Abhängigkeiten ###

Das Bereitstellen einer eigenständigen Bereitstellung mit einer oder mehreren Drittanbieter-Abhängigkeiten umfasst das Hinzufügen der Drittanbieter-Abhängigkeit:

1. Fügen Sie Verweise auf Drittanbieter-Bibliotheken zum `dependencies`-Teil Ihrer `project.json`-Datei hinzu. Der folgende `dependencies`-Abschnitt verwendet Json.NET als Drittanbieter-Bibliothek.

    ```json
    "dependencies": {
      "Microsoft.NETCore.App": "1.0.0",
      "Newtonsoft.Json": "9.0.1"
    },
    ```
2. Wenn noch nicht geschehen, laden Sie das NuGet-Paket mit der Drittanbieter-Abhängigkeit auf Ihr System herunter. Nach dem Hinzufügen der Abhängigkeit, führen Sie den `dotnet restore`-Befehl aus, um über die Abhängigkeit auf Ihrer Anwendung zu verfügen. Da die Abhängigkeit zum Zeitpunkt der Veröffentlichung aus dem lokalen NuGet-Cache aufgelöst wurde, muss sie auf Ihrem System verfügbar sein.

Im folgenden sehen Sie die vollständige project.json-Datei für dieses Projekt:

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable",
    "emitEntryPoint": true
  },
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0",
    "Newtonsoft.Json": "9.0.1"
  },
  "frameworks": {
    "netcoreapp1.0": {
    }
  },
  "runtimes": {
    "win10-x64": {},
    "osx.10.10-x64": {}
  }
}
```

Wenn Sie Ihre Anwendung bereitstellen, sind die Drittanbieter-Abhängigkeiten, die in Ihrer Anwendung verwendet werden, auch in Ihren Anwendungsdateien enthalten. Drittanbieter-Bibliotheken müssen noch nicht auf dem System vorhanden sein, auf dem die Anwendung ausgeführt wird.

Beachten Sie, dass Sie eine eigenständige Bereitstellung mit einer Drittanbieter-Bibliothek nur auf von dieser Bibliothek unterstützten Plattformen bereitstellen können. Dies ist vergleichbar mit Drittanbieter-Abhängigkeiten mit systemeigenen Abhängigkeiten in Ihrer Framework-abhängigen Bereitstellung. 

### <a name="deploying-a-selfcontained-deployment-with-a-smaller-footprint"></a>Bereitstellen einer eigenständigen Bereitstellung mit weniger Speicherbedarf ###

Wenn die Verfügbarkeit von ausreichend Speicherplatz auf den Zielsystemen ein Problem sein könnte, können Sie den allgemeinen Speicherbedarf Ihrer Anwendung durch Ausschließen einiger Systemkomponenten reduzieren. Zu diesem Zweck definieren Sie explizit die .NET Core-Komponenten, die Ihre Anwendung in der Datei project.json enthält.

Befolgen Sie die ersten beiden Schritte für die Erstellung einer eigenständigen Bereitstellung, um eine eigenständigen Bereitstellung mit weniger Speicherbedarf zu erstellen. Nachdem Sie den `dotnet new`-Befehl ausgeführt und den C#-Quellcode für Ihre Anwendung hinzugefügt haben, gehen Sie folgendermaßen vor:

1. Öffnen Sie die `project.json`-Datei und ersetzen Sie den `frameworks`-Abschnitt folgendermaßen:

    ```json
    "frameworks": {
      "netstandard1.6": { }
    }
    ```
Dies bewirkt zweierlei:

    * Es gibt an, dass unsere Anwendung nur die .NET-Standardbibliothek verwendet, anstatt des gesamten `netcoreapp1.0`-Framework einschließlich .NET Core-CLR, der .NET Core-Bibliothek und zahlreichen anderen Systemkomponenten.

    * Das Entfernen des `"type": "platform"`-Attributs gibt an, dass das Framework als eine Reihe von für unsere Anwendung lokalen Komponenten, und nicht als ein systemweites Plattformpaket bereitgestellt wird.

2. Ersetzen Sie den Abschnitt `dependencies` durch Folgendes:

    ```json
    "dependencies": {
      "NETStandard.Library": "1.6.0",
      "Microsoft.NETCore.Runtime.CoreCLR": "1.0.2",
      "Microsoft.NETCore.DotNetHostPolicy":  "1.0.1"
    },
    ```
   Dies definiert die von unserer Anwendung verwendeten Systemkomponenten. Die Systemkomponenten, die mit unserer Anwendung verpackt sind, enthalten die .NET-Standardbibliothek, die .NET Core Runtime und den .NET Core-Host. Dies führt zu einer eigenständigen Bereitstellung mit weniger Speicherbedarf.

3. Wie im Beispiel [Bereitstellen einer einfachen eigenständigen Bereitstellung](#simpleSelf) erstellen Sie einen `runtimes`-Abschnitt in Ihrer `project.json`-Datei, der die Zielplattformen Ihrer Anwendung definiert, und die Runtime-ID für jede Zielplattform angibt. Sie finden eine RID-Liste im [RID-Katalog](../rid-catalog.md). Der folgende `runtimes`-Abschnitt gibt z.B. an, dass die Anwendung auf 64-Bit Windows 10-Betriebssystemen und der 64-Bit OS X-Version 10.10 ausgeführt wird.

    ```json
        "runtimes": {
          "win10-x64": {},
          "osx.10.10-x64": {}
        }
    ```
Beachten Sie, dass Sie auch ein Komma hinzufügen müssen, um den `runtimes`-Abschnitt vom vorherigen Abschnitt zu trennen.
Eine vollständige `project.json`-Beispieldatei wird später in diesem Abschnitt angezeigt.

4. Führen Sie den `dotnet restore`-Befehl aus, um die in Ihrem Projekt angegebenen Abhängigkeiten wiederherzustellen.

5. Erstellen Sie mithilfe des `dotnet build`-Befehls Debugversionen Ihrer Anwendung auf allen Zielplattformen. Wenn Sie den Runtime-ID, den Sie gerne erstellen würden, nicht angeben, erstellt der `dotnet build`-Befehl nur einen Build für die Runtime-ID des aktuellen Systems. Mit den folgenden Befehlen können Sie Ihre Anwendung für beide Zielplattformen erstellen:

    ```console
    dotnet build -r win10-x64
    dotnet build -r osx.10.10-x64
    ```

6. Nachdem Sie die Anwendung debuggt und getestet haben, können Sie die Dateien, die mit Ihrer Anwendung für jede Plattform bereitgestellt werden, erstellen, indem Sie den `dotnet publish`-Befehl für beide Plattformen wie folgt nutzen:

   ```console
   dotnet publish -c release -r win10-x64
   dotnet publish -c release -r osx.10.10-x64
   ```
Dies erstellt eine Releaseversion (anstatt einer Debugversion) Ihrer Anwendung für jede Zielplattform. Die resultierenden Dateien werden in ein Unterverzeichnis namens `publish` platziert, das sich in einem Unterverzeichnis des `.\bin\release\netstandard1.6\<runtime_identifier>`-Unterverzeichnis Ihres Projekts befindet. Beachten Sie, dass jedes Unterverzeichnis den vollständigen Dateisatz enthält (Dateien Ihrer Anwendung und alle .NET Core-Dateien), der zum Starten Ihrer Anwendung erforderlich ist.

7. Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält. Die Datei ist in erster Linie für das Debuggen von Ausnahmen zuständig. Sie können sich dafür entscheiden, sie nicht mit den Dateien Ihrer Anwendung zu verpacken.

Die veröffentlichten Dateien können so bereitgestellt werden, wie Sie möchten. Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen. 

Nachfolgend ist die vollständige `project.json`-Datei für dieses Projekt angegeben.

```json
   {
     "version": "1.0.0-*",
     "buildOptions": {
       "debugType": "portable",
       "emitEntryPoint": true
     },
     "dependencies": {
       "NETStandard.Library": "1.6.0",
       "Microsoft.NETCore.Runtime.CoreCLR": "1.0.2",
       "Microsoft.NETCore.DotNetHostPolicy":  "1.0.1"
     },
     "frameworks": {
       "netstandard1.6": { }
     },
     "runtimes": {
       "win10-x64": {},
       "osx.10.10-x64": {}
     }
   }
```



<!--HONumber=Nov16_HO1-->


