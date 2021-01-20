---
title: Migrieren moderner Desktop Anwendungen
description: Alles, was Sie über den Migrationsprozess für moderne Desktop Anwendungen wissen müssen.
ms.date: 01/19/2021
ms.openlocfilehash: b5bea6e601dc040adfd8ed410320a3416cb3372e
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615762"
---
# <a name="migrating-modern-desktop-applications"></a>Migrieren moderner Desktop Anwendungen

In diesem Kapitel untersuchen wir die häufigsten Probleme und Herausforderungen, die beim Migrieren einer vorhandenen Anwendung von .NET Framework zu .net auftreten können.

Eine komplexe Desktop Anwendung funktioniert nicht isoliert und erfordert eine gewisse Interaktion mit Subsystemen, die sich möglicherweise auf dem lokalen Computer oder auf einem Remote Server befinden. Sie benötigt wahrscheinlich eine Datenbank, um entweder lokal oder Remote eine Verbindung als Persistenzspeicher herzustellen. Mit der Erhöhung der Internet-und Dienst orientierten Architekturen ist es üblich, dass Ihre Anwendung mit einer Art von Diensten verbunden ist, die sich auf einem Remote Server oder in der Cloud befinden. Möglicherweise müssen Sie auf das Dateisystem des Computers zugreifen, um einige Funktionen zu implementieren. Alternativ dazu können Sie auch eine Funktion verwenden, die sich innerhalb eines COM-Objekts außerhalb der Anwendung befindet, was ein häufiges Szenario ist, wenn Sie z. b. Office-Assemblys in Ihre APP integrieren.

Außerdem gibt es Unterschiede in der API-Oberfläche, die von .NET Framework und .net verfügbar gemacht wird, und einige Funktionen, die auf .NET Framework verfügbar sind, sind unter .net nicht verfügbar. Daher ist es wichtig, dass Sie beim Planen einer Migration wissen und berücksichtigen.

## <a name="configuration-files"></a>Konfigurationsdateien

Konfigurationsdateien bieten die Möglichkeit, Gruppen von Eigenschaften zu speichern, die zur Laufzeit gelesen werden, und das Verhalten der apps zu beeinflussen, z. b. wo eine Datenbank gesucht werden soll oder wie oft eine Schleife ausgeführt werden soll. Das schöne an dieser Technik ist, dass Sie einige Aspekte der Anwendung ändern können, ohne dass ein erneutes Kompilieren und erneute Kompilieren erforderlich ist. Dies ist praktisch, wenn beispielsweise derselbe app-Code in einer Entwicklungsumgebung mit einem bestimmten Satz von Konfigurations Werten und in der Produktionsumgebung mit einem anderen ausgeführt wird.

### <a name="configuration-on-net-framework"></a>Konfiguration auf .NET Framework

Wenn Sie über eine funktionierende .NET Framework Desktop Anwendung verfügen, besteht die Wahrscheinlichkeit,  dass Sie über die- <xref:System.Configuration.AppSettingsSection> Klasse aus dem-Namespace auf eineapp.configDatei zugreifen `System.Configuration` .

In der .NET Framework-Infrastruktur gibt es eine Hierarchie von Konfigurationsdateien, die Eigenschaften von den übergeordneten Elementen erben. Sie finden eine *machine.config* Datei, in der viele Eigenschaften und Konfigurations Abschnitte definiert sind, die in einer beliebigen Nachfolger Konfigurationsdatei verwendet oder überschrieben werden können.

### <a name="configuration-on-net"></a>Konfiguration in .net

In der .NET-Welt gibt es keine *machine.config* Datei. Auch wenn Sie den alten, vorgefertigten Namespace weiterhin verwenden können <xref:System.Configuration> , sollten Sie in Erwägung gezogen werden, auf die moderne zu wechseln <xref:Microsoft.Extensions.Configuration> , die eine gute Anzahl von Verbesserungen bietet.

Die Konfigurations-API unterstützt das Konzept des Konfigurations Anbieters, der die Datenquelle definiert, die zum Laden der Konfiguration verwendet werden soll. Es gibt verschiedene Arten von integrierten Anbietern, wie z. b.:

- Speicherinterne .NET Objekte
- INI-Dateien
- JSON-Dateien
- XML-Dateien
- Befehlszeilenargumente
- Umgebungsvariablen
- Verschlüsselter Benutzerspeicher

 Sie können auch eigene erstellen.

Die neue Konfiguration ermöglicht eine Liste von Name-Wert-Paaren, die in einer Hierarchie mit mehreren Ebenen gruppiert werden können. Jeder gespeicherte Wert wird einer Zeichenfolge zugeordnet, und es gibt eine integrierte Bindungs Unterstützung, mit der Sie Einstellungen in ein poco-Objekt (Custom Plain Old CLR Object) deserialisieren können.

Mit dem- <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder> Objekt können Sie beliebig viele Konfigurations Anbieter hinzufügen, die Sie möglicherweise für Ihre Anwendung benötigen, und eine Rang folgen Regel zum Auflösen von Einstellungen verwenden. Der letzte Anbieter, den Sie in Ihrem Code hinzufügen, überschreibt die anderen. Dies ist ein großartiges Feature zum Verwalten verschiedener Umgebungen für die Ausführung, da Sie unterschiedliche Konfigurationen für Entwicklungs-, Test-und Produktionsumgebungen definieren und diese in einer einzelnen Funktion innerhalb Ihres Codes verwalten können.

### <a name="migrating-configuration-files"></a>Migrieren von Konfigurationsdateien

Sie können weiterhin Ihre vorhandene app.config-XML-Datei verwenden. Allerdings können Sie diese Gelegenheit nutzen, um Ihre Konfiguration zu migrieren, um von den verschiedenen Erweiterungen in .net zu profitieren.

Wenn Sie von einem *app.config* im alten Stil zu einer neuen Konfigurationsdatei migrieren möchten, sollten Sie zwischen einem XML-Format und einem JSON-Format wählen.

Wenn Sie XML auswählen, ist die Konvertierung unkompliziert. Da der Inhalt identisch ist, speichern Sie die *app.config* Datei einfach mit XML als Typ. Ändern Sie dann den Code, der auf appSettings verweist, um die-Klasse zu verwenden `ConfigurationBuilder` . Diese Änderung sollte einfach sein.

Wenn Sie ein JSON-Format verwenden möchten, das Sie nicht per Hand migrieren möchten, ist ein Tool mit dem Namen " [dotnet-config2json](https://www.nuget.org/packages/dotnet-config2json/) " in .net verfügbar, mit dem eine *app.config* Datei in eine JSON-Konfigurationsdatei konvertiert werden kann.

Möglicherweise treten auch einige Probleme auf, wenn Sie Konfigurations Abschnitte verwenden, die in der *machine.config* -Datei definiert wurden. Sehen Sie sich beispielsweise die folgende Konfiguration an:

```xml
<configuration>
    <system.diagnostics>
        <switches>
            <add name="General" value="4" />
        </switches>
        <trace autoflush="true" indentsize="2">
            <listeners>
                <add name="myListener"
                     type="System.Diagnostics.TextWriterTraceListener,
                           System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
                     initializeData="MyListener.log"
                     traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />
            </listeners>
        </trace>
    </system.diagnostics>
</configuration>
```

Wenn Sie diese Konfiguration für .NET verwenden, erhalten Sie eine Ausnahme:

> Unbekannter Konfigurations Abschnitt System. Diagnostics

Diese Ausnahme tritt auf, weil dieser Abschnitt und die Assembly, die für die Verarbeitung dieses Abschnitts zuständig sind, in der *machine.config* -Datei definiert wurden, die jetzt nicht vorhanden ist.

Um das Problem zu beheben, können Sie die Abschnitts Definition aus der alten *machine.config* in die neue Konfigurationsdatei kopieren:

```xml
<configSections>
    <section name="system.diagnostics"
             type="System.Diagnostics.SystemDiagnosticsSection,
                   System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
</configSections>
```

## <a name="accessing-databases"></a>Zugreifen auf Datenbanken

Fast jede Desktop Anwendung benötigt eine beliebige Datenbank. Für den Desktop ist es üblich, Client/Server-Architekturen mit einer direkten Verbindung zwischen der Desktop-App und der Datenbank-Engine zu finden. Diese Datenbanken können lokal oder Remote sein, abhängig davon, wie Informationen zwischen verschiedenen Benutzern gemeinsam genutzt werden müssen.

Aus Sicht des Codes gibt es viele Technologien und Frameworks, die dem Entwickler die Möglichkeit bieten, eine Verbindung, Abfrage und Aktualisierung einer Datenbank herzustellen.

Die häufigsten Beispiele für die-Datenbank, die Sie bei der Kommunikation mit Windows-Desktop Anwendungen finden, sind Microsoft Access und Microsoft SQL Server. Wenn Sie mehr als 20 Jahre Erfahrung beim Programmieren für den Desktop haben, sind Namen wie ODBC, OLEDB, RDO, ADO, ADO.net, LINQ und Entity Framework gut vertraut.

### <a name="odbc"></a>ODBC

Sie können ODBC weiterhin in .NET verwenden, da Microsoft die Bibliothek bereitstellt, die `System.Data.Odbc` mit .NET Standard 2,0 kompatibel ist.

### <a name="ole-db"></a>OLE DB

[OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85)) war eine großartige Möglichkeit, auf eine einheitliche Weise auf verschiedene Datenquellen zuzugreifen. Es basiert aber auf com, eine reine Windows-Technologie, die daher nicht die beste Lösung für eine plattformübergreifende Technologie wie z. b. .net war. Außerdem wird Sie in SQL Server, Version 2014 und höher, nicht unterstützt. Aus diesen Gründen werden OLE DB von .net nicht unterstützt.

### <a name="adonet"></a>ADO.NET

Sie können ADO.net weiterhin aus Ihrem vorhandenen Desktop Code in .NET verwenden. Sie müssen nur einige nuget-Pakete aktualisieren.

### <a name="ef-core-vs-ef6"></a>EF Core im Vergleich zu EF6

Es gibt zwei derzeit unterstützte Versionen von Entity Framework (EF), Entity Framework 6 (EF6) und EF Core.

Die neueste als Teil der .NET Framework Welt veröffentlichte Technologie ist Entity Framework, wobei 6,4 die neueste Version ist. Mit der Einführung von .net Core veröffentlichte Microsoft auch einen neuen Datenzugriffs Stapel, der auf Entity Framework basiert und Entity Framework Core genannt wird.

Sie können EF 6,4 und EF Core aus .NET Framework und .NET verwenden. Was sind die Entscheidungs Treiber, die Sie bei der Entscheidung unterstützen?

EF 6,3 ist die erste Version von EF6, die auf .NET ausgeführt werden kann und plattformübergreifend funktioniert. Das Hauptziel dieser Version bestand darin, vorhandene Anwendungen, die EF6 verwenden, zu .net zu migrieren.

EF Core wurde entwickelt, um eine ähnliche Entwicklererfahrung wie EF6 bereitzustellen. Die meisten APIs der obersten Ebene bleibt unverändert, so dass EF Core Entwicklern, die EF 6 verwendet haben, vertraut erscheint.

Obwohl es kompatibel ist, gibt es Unterschiede bei der Implementierung, die Sie vor dem Treffen der Entscheidung überprüfen sollten.
Weitere Informationen finden Sie unter [Compare EF Core & EF6](/ef/efcore-and-ef6/).

Es wird empfohlen, EF Core if:

* Die APP benötigt die Funktionen von .net.
* EF Core unterstützt alle Funktionen, die für die App erforderlich sind.

Ziehen Sie EF6 in Erwägung, wenn die beiden folgenden Bedingungen erfüllt sind:

* Die APP kann unter Windows und .NET Framework 4,0 oder höher ausgeführt werden.
* EF6 unterstützt alle Funktionen, die für die App erforderlich sind.

### <a name="relational-databases"></a>Relationale Datenbanken

#### <a name="sql-server"></a>SQL Server

SQL Server ist eine der bevorzugten Datenbanken, wenn Sie vor einigen Jahren für den Desktop entwickelt wurden. Mit der Verwendung von <xref:System.Data.SqlClient> in .NET Framework können Sie auf Versionen von SQL Server zugreifen, die datenbankspezifische Protokolle kapseln.

In .net finden Sie eine neue `SqlClient` Klasse, die vollständig mit der in der .NET Framework vorhandenen kompatibel ist, jedoch in der <xref:Microsoft.Data.SqlClient> Bibliothek gespeichert ist. Sie müssen lediglich einen Verweis auf das nuget-Paket " [Microsoft. Data. SqlClient](https://www.nuget.org/packages/Microsoft.Data.SqlClient/) " hinzufügen und einige Umbenennungen für die Namespaces durchführen, und alles sollte erwartungsgemäß funktionieren.

#### <a name="microsoft-access"></a>Microsoft Access

Microsoft Access wurde seit Jahren verwendet, als die ausgereifte und skalierbare SQL Server nicht benötigt wurden. Mithilfe der-Bibliothek können Sie weiterhin eine Verbindung mit Microsoft Access herstellen <xref:System.Data.Odbc> .

## <a name="consuming-services"></a>Nutzen von Diensten

Mit der Erhöhung der Dienst orientierten Architekturen begann sich die Entwicklung von Desktop Anwendungen von einem Client-Server-Modell zum Ansatz mit drei Ebenen. Beim Client-Server-Ansatz wird eine direkte Datenbankverbindung vom Client hergestellt, der die Geschäftslogik enthält, in der Regel in einer einzelnen exe-Datei. Andererseits richtet der Ansatz mit drei Ebenen eine zwischengeschaltete Dienst Schicht ein, die Geschäftslogik-und Datenbankzugriffe implementiert und eine bessere Sicherheit, Skalierbarkeit und Wiederverwendbarkeit ermöglicht. Anstatt direkt mit Datasets von Daten zu arbeiten, basiert der ebenenansatz auf einer Reihe von Diensten, die Verträge implementieren und Objekte als Möglichkeit zum Implementieren der Datenübertragung implementieren.

Wenn Sie über eine Desktop Anwendung verfügen, die einen WCF-Dienst verwendet und Sie zu .NET migrieren möchten, müssen Sie einige Punkte beachten.

Der erste Schritt besteht darin, die Konfiguration für den Zugriff auf den Dienst aufzulösen. Da sich die Konfiguration in .NET unterscheidet, müssen Sie einige Updates in der Konfigurationsdatei vornehmen.

Zweitens müssen Sie den Dienst Client mit den neuen Tools neu generieren, die in Visual Studio 2019 vorhanden sind. In diesem Schritt müssen Sie in Erwägung gezogen werden, die Generierung der synchronen Vorgänge zu aktivieren, damit der Client mit vorhandenem Code kompatibel ist.

Wenn Sie nach der Migration feststellen, dass Bibliotheken vorhanden sind, die nicht in .net vorhanden sind, können Sie einen Verweis auf das nuget-Paket [Microsoft. Windows. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) hinzufügen und überprüfen, ob die fehlenden Funktionen vorhanden sind.

Wenn Sie die- <xref:System.Net.WebRequest> Klasse zum Ausführen von Webdienst aufrufen verwenden, finden Sie möglicherweise einige Unterschiede zu .net. Es wird empfohlen, stattdessen den System .net. http. HttpClient zu verwenden.

## <a name="consuming-a-com-object"></a>Verwenden eines COM-Objekts

Derzeit gibt es keine Möglichkeit, einen Verweis auf ein COM-Objekt aus Visual Studio 2019 für die Verwendung mit .net hinzuzufügen. Daher müssen Sie die Projektdatei manuell ändern.

Fügen Sie eine `COMReference` Struktur in die Projektdatei ein, wie im folgenden Beispiel gezeigt:

```xml
<ItemGroup>
    <COMReference Include="MSHTML">
        <Guid>{3050F1C5-98B5-11CF-BB82-00AA00BDCE0B}\</Guid>
        <VersionMajor>4</VersionMajor>
        <VersionMinor>0</VersionMinor>
        <Lcid>0</Lcid>
        <WrapperTool>primary</WrapperTool>
        <Isolated>false</Isolated>
    </COMReference>
</ItemGroup>
```

## <a name="more-things-to-consider"></a>Weitere zu berücksichtigende Punkte

Mehrere für .NET Framework Bibliotheken verfügbare Technologien sind für .net Core oder .net 5 nicht verfügbar. Wenn Ihr Code von einigen dieser Technologien abhängig ist, sollten Sie die in diesem Abschnitt beschriebenen alternativen Ansätze beachten.

Das [Windows-Kompatibilitätspaket](../../core/porting/windows-compat-pack.md) bietet Zugriff auf APIs, die zuvor nur für .NET Framework verfügbar waren. Sie kann in .net Core-und .NET Standard-Projekten verwendet werden.

Weitere Informationen zur API-Kompatibilität finden Sie in der Dokumentation zu wichtigen Änderungen und veralteten/veralteten APIs unter <https://docs.microsoft.com/dotnet/core/compatibility/fx-core> .

### <a name="appdomains"></a>AppDomains

Anwendungsdomänen (AppDomains) isolieren Apps voneinander. AppDomains erfordern eine Laufzeitunterstützung und sind aufwändig. Das Erstellen zusätzlicher App-Domänen wird nicht unterstützt. Für die Codeisolierung empfehlen wir separate Prozesse oder die Verwendung von Containern als Alternative. Für das dynamische Laden von Assemblys wird die neue Klasse <xref:System.Runtime.Loader.AssemblyLoadContext> empfohlen.

Um die Code Migration von .NET Framework zu vereinfachen, macht .net einen Teil der `AppDomain` API-Oberfläche verfügbar. Manche Elemente der APIs funktionieren normal (z.B. <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), einige Member führen keine Aktion aus (z.B. <xref:System.AppDomain.SetCachePath%2A>), und einige davon lösen <xref:System.PlatformNotSupportedException> aus (z.B. <xref:System.AppDomain.CreateDomain%2A>).

### <a name="remoting"></a>Remoting

.NET-Remoting wurde für die AppDomain-Kommunikation verwendet, die nicht mehr unterstützt wird. Darüber hinaus erfordert Remoting die Runtimeunterstützung, die teuer in der Wartung ist. Aus diesen Gründen wird .NET-Remoting unter .net nicht unterstützt.

Für die prozessübergreifende Kommunikation sollten Sie Mechanismen für die prozessübergreifende Kommunikation (Inter-Process Communication, IPC) als Alternative zu Remoting, wie z <xref:System.IO.Pipes?displayProperty=nameWithType> . b. oder der-Klasse, berücksichtigen <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> .

Verwenden Sie computerübergreifend eine netzwerkbasierte Lösung als Alternative. Verwenden Sie vorzugsweise ein nur-Text-Protokoll mit geringem Overhead, z. b. http. Der Kestrel Webserver, der von ASP.NET Core verwendete Webserver, ist hier eine Option.

### <a name="code-access-security-cas"></a>Codezugriffssicherheit (Code Access Security, CAS)

Das Sandboxing, das auf der Laufzeit oder dem Framework basiert, um einzuschränken, welche Ressourcen von einer verwalteten Anwendung oder Bibliothek verwendet bzw. ausgeführt werden, wird unter .net nicht unterstützt.

Verwenden Sie Sicherheitsgrenzen, die vom Betriebssystem bereitgestellt werden, z. b. Virtualisierung, Container oder Benutzerkonten zum Ausführen von Prozessen mit dem minimalen Berechtigungs Satz.

### <a name="security-transparency"></a>Sicherheitstransparenz

Ähnlich wie CAS trennt die Sicherheitstransparenz den Sandboxcode von sicherheitsrelevantem Code in einer deklarativen Weise, aber sie wird nicht mehr als Sicherheitsgrenze unterstützt.

Verwenden Sie Sicherheitsgrenzen, die vom Betriebssystem bereitgestellt werden, z. b. Virtualisierung, Container oder Benutzerkonten zum Ausführen von Prozessen mit dem geringsten Berechtigungs Satz.

>[!div class="step-by-step"]
>[Zurück](whats-new-dotnet.md )
>[Weiter](windows-migration.md)
