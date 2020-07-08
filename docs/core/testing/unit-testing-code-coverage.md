---
title: Verwenden von Code Coverage für Komponententests
description: Hier erfahren Sie, wie Sie die Code-Coverage-Funktionen für .NET-Komponententests verwenden.
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.openlocfilehash: af64116e86c3f46f37c8d5d079b9c86084095485
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853900"
---
# <a name="use-code-coverage-for-unit-testing"></a>Verwenden von Code Coverage für Komponententests

Komponententests helfen beim Sicherstellen der Funktionalität und bieten eine Überprüfungsmethode für das Refactoring. Code Coverage ist eine Messung der Codemenge, die von Komponententests ausgeführt wird. Dabei kann es sich um Zeilen, Branches oder Methoden handeln. Wenn Sie beispielsweise über eine einfache Anwendung mit nur zwei bedingten Codebranches (_Branch a_ und _Branch b_) verfügen, wird bei einem Komponententest, der den bedingten _Branch a_ überprüft, eine Code Coverage des Branchs von 50 % gemeldet.

In diesem Artikel werden die Verwendung von Code Coverage für Komponententests mit Coverlet sowie die Berichtsgenerierung mithilfe von ReportGenerator erläutert. Der Fokus dieses Artikels liegt auf C# und xUnit als Testframework. Es funktioniert aber auch mit MSTest und NUnit. Coverlet ist ein [Open-Source-Projekt auf GitHub](https://github.com/coverlet-coverage/coverlet), das ein plattformübergreifendes Code-Coverage-Framework für C# bereitstellt. [Coverlet](https://dotnetfoundation.org/projects/coverlet) ist Teil der .NET Foundation. Coverlet sammelt Code-Coverage-Testlaufdaten von Cobertura, die für die Berichtsgenerierung verwendet werden.

Außerdem wird in diesem Artikel erläutert, wie die Code-Coverage-Informationen, die von einem Coverlet-Testlauf gesammelt wurden, zum Generieren eines Berichts verwendet werden. Die Berichtsgenerierung ist mithilfe eines anderen [Open-Source-Projekts auf GitHub, ReportGenerator,](https://github.com/danielpalme/ReportGenerator) möglich. ReportGenerator wandelt von Cobertura und vielen anderen generierte Coverageberichte in für Menschen lesbare Berichte in unterschiedlichen Formaten um.

Dieser Artikel basiert auf dem [Beispiequellcodeprojekt](https://docs.microsoft.com/samples/dotnet/samples/unit-testing-code-coverage-cs), das im Beispielbrowser verfügbar ist.

## <a name="system-under-test"></a>Getestetes System

„Getestetes System“ bezieht sich auf den Code, für den Sie Komponententests schreiben. Dabei kann es sich um Objekte, Dienste oder alles andere handeln, das über testbare Funktionen verfügt. Im Rahmen dieses Artikels erstellen Sie eine Klassenbibliothek, die das getestete System darstellt, sowie zwei entsprechende Komponententestprojekte.

### <a name="create-a-class-library"></a>Erstellen einer Klassenbibliothek

Erstellen Sie über eine Eingabeaufforderung in einem neuen Verzeichnis mit dem Namen `UnitTestingCodeCoverage` mithilfe des Befehls [`dotnet new classlib`](../tools/dotnet-new.md#classlib) eine neue .NET Standard-Klassenbibliothek:

```dotnetcli
dotnet new classlib -n Numbers
```

Der folgende Codeausschnitt definiert eine einfache `PrimeService`-Klasse, die Funktionen bereitstellt, um zu prüfen, ob eine Zahl eine Primzahl ist. Kopieren Sie den folgenden Codeausschnitt, und ersetzen Sie den Inhalt der Datei *Class1.cs*, die automatisch im Verzeichnis *Numbers* (Zahlen) erstellt wurde. Benennen Sie die Datei *Class1.cs* in *PrimeService.cs* um.

```csharp
namespace System.Numbers
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            if (candidate < 2)
            {
                return false;
            }

            for (int divisor = 2; divisor <= Math.Sqrt(candidate); ++divisor)
            {
                if (candidate % divisor == 0)
                {
                    return false;
                }
            }
            return true;
        }
    }
}
```

> [!TIP]
> Es sollte erwähnt werden, dass die `Numbers`-Klassenbibliothek absichtlich dem `System`-Namespace hinzugefügt wurde. Dies ermöglicht, dass <xref:System.Math?displayProperty=fullName> ohne eine `using System;`-Namespacedeklaration zugänglich ist. Weitere Informationen finden Sie unter [Namespace (C#-Referenz)](../../csharp/language-reference/keywords/namespace.md).

### <a name="create-test-projects"></a>Erstellen von Testprojekten

Erstellen Sie über dieselbe Eingabeaufforderung mit dem Befehl [`dotnet new xunit`](../tools/dotnet-new.md#test) zwei neue **xUnit-Testprojekt (.NET Core)** -Vorlagen:

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.Collector
```

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.MSBuild
```

Beide neu erstellten xUnit-Testprojekte müssen einen Projektverweis der *Numbers*-Klassenbibliothek hinzufügen. Dies ist erforderlich, damit die Testprojekte zum Testen auf *PrimeService* zugreifen können. Verwenden Sie in der Eingabeaufforderung den Befehl [`dotnet add`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add XUnit.Coverlet.Collector\XUnit.Coverlet.Collector.csproj reference Numbers\Numbers.csproj
```

```dotnetcli
dotnet add XUnit.Coverlet.MSBuild\XUnit.Coverlet.MSBuild.csproj reference Numbers\Numbers.csproj
```

Das *MSBuild*-Projekt wird entsprechend benannt, da es vom NuGet-Paket [coverlet.msbuild](https://www.nuget.org/packages/coverlet.msbuild) abhängen wird. Fügen Sie diese Paketabhängigkeit hinzu, indem Sie den Befehl [`dotnet add package`](../tools/dotnet-add-package.md) ausführen:

```dotnetcli
cd XUnit.Coverlet.MSBuild && dotnet add package coverlet.msbuild && cd ..
```

Mit dem vorherigen Befehl wurden Verzeichnisse geändert, wobei der Bereich effektiv auf das *MSBuild*-Testprojekt beschränkt und dann das NuGet-Paket hinzugefügt wurde. Anschließend wurden die Verzeichnisse geändert und um eine Ebene erhöht.

Öffnen Sie beide *UnitTest1.cs*-Dateien, und ersetzen Sie deren Inhalt durch den folgenden Codeausschnitt. Benennen Sie die *UnitTest1.cs*-Dateien in *PrimeServiceTests.cs* um.

```csharp
using System.Numbers;
using Xunit;

namespace XUnit.Coverlet
{
    public class PrimeServiceTests
    {
        readonly PrimeService _primeService;

        public PrimeServiceTests() => _primeService = new PrimeService();

        [
            Theory,
            InlineData(-1), InlineData(0), InlineData(1)
        ]
        public void IsPrime_ValuesLessThan2_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");

        [
            Theory,
            InlineData(2), InlineData(3), InlineData(5), InlineData(7)
        ]
        public void IsPrime_PrimesLessThan10_ReturnTrue(int value) =>
            Assert.True(_primeService.IsPrime(value), $"{value} should be prime");

        [
            Theory,
            InlineData(4), InlineData(6), InlineData(8), InlineData(9)
        ]
        public void IsPrime_NonPrimesLessThan10_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");
    }
}
```

### <a name="create-a-solution"></a>Erstellen einer Projektmappe

Erstellen Sie über die Eingabeaufforderung eine neue Projektmappe, um die Klassenbibliothek und die beiden Testprojekte zu kapseln. Verwenden Sie hierzu den [`dotnet sln`](../tools/dotnet-sln.md)-Befehl:

```dotnetcli
dotnet new sln -n XUnit.Coverage
```

Dadurch wird ein neuer Projektmappen-Dateiname `XUnit.Coverage` im Verzeichnis *UnitTestingCodeCoverage* erstellt. Fügen Sie die Projekte dem Stamm der Projektmappe hinzu.

## <a name="linux"></a>[Linux](#tab/linux)

```dotnetcli
dotnet sln XUnit.Coverage.sln add **/*.csproj --in-root
```

## <a name="windows"></a>[Windows](#tab/windows)

```dotnetcli
dotnet sln XUnit.Coverage.sln add (ls **/*.csproj) --in-root
```

---

Erstellen Sie die Projektmappe mithilfe des [`dotnet build`](../tools/dotnet-build.md)-Befehls:

```dotnetcli
dotnet build
```

Wenn der Build erfolgreich ist, haben Sie die drei Projekte erstellt, ordnungsgemäß auf die Projekte und Pakete verwiesen und den Quellcode richtig aktualisiert. Und das war‘s schon.

## <a name="tooling"></a>Tools

Es gibt zwei Arten von Code-Coverage-Tools:

- **DataCollectors:** DataCollectors (Datensammler) überwachen die Testausführung und sammeln Informationen zu Testläufen. Sie melden die gesammelten Informationen in verschiedenen Ausgabeformaten, z. B. XML und JSON. Weitere Informationen finden Sie unter [Ihr erster DataCollector](https://github.com/Microsoft/vstest-docs/blob/master/docs/extensions/datacollector.md).
- **Berichtsgeneratoren:** Verwenden Sie die bei Testläufen gesammelten Daten zum Generieren von Berichten, die oft in Form von formatierten HTML-Dateien vorliegen.

In diesem Abschnitt liegt der Schwerpunkt auf den Datensammlertools. Wenn Sie Coverlet für die Code Coverage verwenden möchten, muss ein vorhandenes Komponententestprojekt die entsprechenden Paketabhängigkeiten aufweisen. Alternativ muss es auf [globalen .NET-Tools](../tools/global-tools.md) und dem entsprechenden [coverlet.console](https://www.nuget.org/packages/coverlet.console)-NuGet-Paket basieren.

## <a name="integrate-with-net-test"></a>Integration mit .NET-Test

Die Vorlage des xUnit-Testprojekts ist standardmäßig bereits mit [coverlet.collector](https://www.nuget.org/packages/coverlet.collector) integriert.
Wechseln Sie über die Eingabeaufforderung in das Verzeichnis des *XUnit.Coverlet.Collector*-Projekts, und führen Sie den [`dotnet test`](../tools/dotnet-test.md)-Befehl aus:

```dotnetcli
cd XUnit.Coverlet.Collector && dotnet test --collect:"XPlat Code Coverage"
```

> [!NOTE]
> Das `"XPlat Code Coverage"`-Argument ist ein Anzeigename, der den Datensammlern von Coverlet entspricht. Dieser Name ist erforderlich, die Groß-/Kleinschreibung wird jedoch nicht beachtet.

Bei der Ausführung von `dotnet test` wird eine resultierende *coverage.cobertura.xml*-Datei im Verzeichnis *TestResults* ausgegeben. Die XML-Datei enthält die Ergebnisse. Diese plattformübergreifende Option basiert auf der .NET Core-CLI und eignet sich sehr gut für Buildsysteme, in denen MSBuild nicht verfügbar ist.

Nachfolgend finden Sie die *coverage.cobertura.xml*-Beispieldatei.

```xml
<?xml version="1.0" encoding="utf-8"?>
<coverage line-rate="1" branch-rate="1" version="1.9" timestamp="1592248008"
          lines-covered="12" lines-valid="12" branches-covered="6" branches-valid="6">
  <sources>
    <source>C:\</source>
  </sources>
  <packages>
    <package name="Numbers" line-rate="1" branch-rate="1" complexity="6">
      <classes>
        <class name="Numbers.PrimeService" line-rate="1" branch-rate="1" complexity="6"
               filename="Numbers\PrimeService.cs">
          <methods>
            <method name="IsPrime" signature="(System.Int32)" line-rate="1"
                    branch-rate="1" complexity="6">
              <lines>
                <line number="8" hits="11" branch="False" />
                <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="7" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="10" hits="3" branch="False" />
                <line number="11" hits="3" branch="False" />
                <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="57" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="15" hits="7" branch="False" />
                <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="27" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="17" hits="4" branch="False" />
                <line number="18" hits="4" branch="False" />
                <line number="20" hits="3" branch="False" />
                <line number="21" hits="4" branch="False" />
                <line number="23" hits="11" branch="False" />
              </lines>
            </method>
          </methods>
          <lines>
            <line number="8" hits="11" branch="False" />
            <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="7" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="10" hits="3" branch="False" />
            <line number="11" hits="3" branch="False" />
            <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="57" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="15" hits="7" branch="False" />
            <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="27" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="17" hits="4" branch="False" />
            <line number="18" hits="4" branch="False" />
            <line number="20" hits="3" branch="False" />
            <line number="21" hits="4" branch="False" />
            <line number="23" hits="11" branch="False" />
          </lines>
        </class>
      </classes>
    </package>
  </packages>
</coverage>
```

> [!TIP]
> Alternativ könnten Sie das MSBuild-Paket verwenden, wenn Ihr Buildsystem bereits MSBuild verwendet. Wechseln Sie über die Eingabeaufforderung in das Verzeichnis des *XUnit.Coverlet.MSBuild*-Projekts, und führen Sie den `dotnet test`-Befehl aus:
>
> ```dotnetcli
> dotnet test /p:CollectCoverage=true /p:CoverletOutputFormat=cobertura
> ```
>
> Die resultierende *coverage.cobertura.xml*-Datei wird ausgegeben.  
> Einen Leitfaden zur MSBuild-Integration finden Sie [hier](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/MSBuildIntegration.md).

## <a name="generate-reports"></a>Generieren von Berichten

Da das Sammeln von Daten aus Komponententestläufen nun möglich ist, können Sie mithilfe von [ReportGenerator](https://github.com/danielpalme/ReportGenerator) Berichte generieren. Verwenden Sie den [`dotnet tool install`](../tools/dotnet-tool-install.md)-Befehl, um das NuGet-Paket [ReportGenerator](https://www.nuget.org/packages/dotnet-reportgenerator-globaltool) als [globales .NET-Tool](../tools/global-tools.md) zu installieren:

```dotnetcli
dotnet tool install -g dotnet-reportgenerator-globaltool
```

Führen Sie das Tool aus, und geben Sie die gewünschten Optionen mit der *coverage.cobertura.xml*-Ausgabedatei aus dem vorherigen Testlauf an.

```console
reportgenerator
"-reports:Path\To\TestProject\TestResults\{guid}\coverage.cobertura.xml"
"-targetdir:coveragereport"
-reporttypes:Html
```

Nachdem Sie diesen Befehl ausgeführt haben, stellt eine HTML-Datei den generierten Bericht dar.

:::image type="content" source="media/test-report.png" lightbox="media/test-report.png" alt-text="Mithilfe des Komponententests generierter Bericht":::

## <a name="see-also"></a>Siehe auch

- [Code Coverage in der Visual Studio-Dokumentation](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested)
- [GitHub-Repository „Coverlet“](https://github.com/coverlet-coverage/coverlet)
- [GitHub-Repository „ReportGenerator“](https://github.com/danielpalme/ReportGenerator)
- [Projektwebsite zu ReportGenerator](https://danielpalme.github.io/ReportGenerator)
- [Testbefehl in der Dokumentation zur .NET Core-CLI](../tools/dotnet-test.md)
- [Beispielquellcode](https://docs.microsoft.com/samples/dotnet/samples/unit-testing-code-coverage-cs)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Bewährte Methoden für Komponententests](unit-testing-best-practices.md)
