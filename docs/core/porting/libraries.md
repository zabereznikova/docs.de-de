---
title: Portieren auf .NET Core – Bibliotheken
description: Erfahren Sie, wie Sie Bibliotheksprojekte von .NET Framework zu .NET Core portieren.
author: cartermp
ms.author: mairaw
ms.date: 07/14/2017
ms.openlocfilehash: eb6b8506d8df218a053242cd0b8d3097fa6d9fd3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199850"
---
# <a name="porting-to-net-core---libraries"></a>Portieren auf .NET Core – Bibliotheken

In diesem Artikel wird die Portierung von Bibliothekscode zu .NET Core beschrieben, damit er plattformübergreifend ausgeführt wird.

## <a name="prerequisites"></a>Erforderliche Komponenten

In diesem Artikel wird vorausgesetzt, dass:

- Sie Visual Studio 2017 oder höher verwenden.
  - .NET Core in früheren Versionen von Visual Studio nicht unterstützt wird.
- Sie den [empfohlenen Portierungsprozess](index.md) verstehen.
- Sie alle Probleme mit [Abhängigkeiten von Drittanbietern](third-party-deps.md) gelöst haben.

Sie sollten sich auch mit dem Inhalt in den folgenden Themen vertraut machen:

[.NET-Standard](~/docs/standard/net-standard.md)   
Dieses Thema beschreibt die formale Spezifikation von .NET-APIs, die in allen .NET-Implementierungen verfügbar sein sollen.

[Pakete, Metapakete und Frameworks](~/docs/core/packages.md)   
In diesem Artikel wird erläutert, wie .NET Core Pakete definiert und verwendet und wie Pakete Code unterstützen, der in mehreren .NET-Implementierungen ausgeführt wird.

[Entwickeln von Bibliotheken mit plattformübergreifenden Tools](~/docs/core/tutorials/libraries.md)   
Dieses Thema erläutert, wie Sie mithilfe von plattformübergreifenden CLI-Tools Bibliotheken für .NET schreiben.

[Erweiterungen des *CSPROJ*-Formats für .NET Core](~/docs/core/tools/csproj.md)   
In diesem Artikel werden die Änderungen erläutert, die an die Projektdateien beim Wechsel zu *csproj* und MSBuild hinzugefügt wurden.

[Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern](~/docs/core/porting/third-party-deps.md)   
In diesem Thema wird die Portabilität von Drittanbieterabhängigkeiten diskutiert und was Sie tun, wenn die Abhängigkeit eines NuGet-Pakets für .NET Core nicht ausgeführt wird.

## <a name="net-framework-technologies-unavailable-on-net-core"></a>.NET Framework-Technologien, die auf .NET Core nicht verfügbar sind

Einige Technologien, die für .NET Framework-Bibliotheken verfügbar sind, sind für die Verwendung mit .NET Core nicht verfügbar, z.B. AppDomains, Remoting, Codezugriffssicherheit (Code Access Security, CAS) und Sicherheitstransparenz. Wenn Ihre Bibliotheken eine oder mehrere dieser Technologien benötigen, sollten Sie die unten beschriebenen alternativen Ansätze in Erwägung ziehen. Für weitere Informationen zur API-Kompatibilität verwaltet das CoreFX-Team eine [Liste von verhaltensbasierten Änderungen/Kompatibilitätsunterbrechungen und veraltete/ältere APIs](https://github.com/dotnet/corefx/wiki/ApiCompat) auf GitHub.

Nur weil eine API oder Technologie derzeit nicht implementiert ist, bedeutet dies nicht zwangsläufig, dass sie absichtlich nicht unterstützt wird. Melden Sie ein Problem in den [dotnet/CoreFX-Repositoryproblemen](https://github.com/dotnet/corefx/issues) auf GitHub, um bestimmte APIs und Technologien anzufordern. [Portierte Anfragen in den Problemen](https://github.com/dotnet/corefx/labels/port-to-core) sind mit der Bezeichnung `port-to-core` markiert.

### <a name="appdomains"></a>AppDomains

AppDomains isoliert Apps voneinander. AppDomains benötigen eine Runtimeunterstützung und sind im Allgemeinen sehr teuer. Sie sind nicht in .NET Core implementiert. Wir planen nicht, diese Funktion in Zukunft hinzuzufügen. Für die Codeisolierung empfehlen wir separate Prozesse oder die Verwendung von Containern als Alternative. Für das dynamische Laden von Assemblys wird die neue Klasse <xref:System.Runtime.Loader.AssemblyLoadContext> empfohlen.

Um die Codemigration von .NET Framework verständlicher zu gestalten, haben wir einiges der <xref:System.AppDomain>-API-Oberfläche in .NET Core verfügbar gemacht. Manche Elemente der API funktionieren normal (z.B. <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), einige Member führen keine Aktion aus (z.B. <xref:System.AppDomain.SetCachePath%2A>), und einige davon lösen <xref:System.PlatformNotSupportedException> aus (z.B. <xref:System.AppDomain.CreateDomain%2A>). Überprüfen Sie die Typen, die Sie für die [`System.AppDomain`-Verweisquelle](https://github.com/dotnet/corefx/blob/master/src/System.Runtime.Extensions/src/System/AppDomain.cs) im [dotnet/CoreFX-GitHub-Repository](https://github.com/dotnet/corefx) verwenden. Stellen Sie dabei sicher, dass Sie den Branch auswählen, der mit Ihrer implementierten Version übereinstimmt.

### <a name="remoting"></a>Remoting

.NET-Remoting wurde als eine problematische Architektur identifiziert. Es wird für die AppDomain-übergreifende Kommunikation verwendet, die nicht mehr unterstützt wird. Darüber hinaus erfordert Remoting die Runtimeunterstützung, die teuer in der Wartung ist. Aus diesen Gründen wird .NET-Remoting auf .NET Core nicht unterstützt, und wir planen nicht, zukünftig eine Unterstützung dafür hinzuzufügen.

Für die Kommunikation zwischen Prozessen sollten Sie die Mechanismen der prozessübergreifenden Kommunikation (interprocess communication, IPC) als Alternative zu Remoting berücksichtigen, zB die Klassen <xref:System.IO.Pipes> oder <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>.

Verwenden Sie computerübergreifend eine netzwerkbasierte Lösung als Alternative. Verwenden Sie vorzugsweise ein Nur-Text-Protokoll mit geringem Verwaltungsaufwand, z.B. HTTP. Der [Kestrel Webserver](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), der von ASP.NET Core verwendete Webserver, ist hier eine Option. Ziehen Sie auch die Verwendung von <xref:System.Net.Sockets> für netzwerkbasierte, computerübergreifende Szenarios in Erwägung. Weitere Optionen finden Sie unter [.NET Open Source Developer Projects: Messaging (.NET Open Source-Entwicklerprojekte: Messaging)](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging).

### <a name="code-access-security-cas"></a>Codezugriffssicherheit (Code Access Security, CAS)

Das Verwenden einer Sandbox, das sich auf die Runtime oder das Framework verlässt, um einzuschränken, welche Ressourcen eine verwaltete Anwendung oder Bibliothek verwendet oder ausführt, [wird in .NET Framework nicht unterstützt](~/docs/framework/misc/code-access-security.md). Daher wird es auch in .NET Core nicht unterstützt. Wir glauben, dass es zu viele Fälle im .NET Framework und in der Runtime gibt, in denen eine Rechteerweiterung CAS weiterhin als Sicherheitsgrenze behandelt. Darüber hinaus macht CAS die Implementierung komplizierter und führt oft zu Auswirkungen auf die Leistung der Korrektheitsprüfung für Anwendungen, die dies nicht verwenden sollen.

Verwenden Sie vom Betriebssystem bereitgestellte Sicherheitsgrenzen, wie Virtualisierung, Container oder Benutzerkonten zum Ausführen von Prozessen mit den geringsten Rechten.

### <a name="security-transparency"></a>Sicherheitstransparenz

Ähnlich wie CAS ermöglicht die Sicherheitstransparenz das Trennen von Sandboxcode von sicherheitsrelevantem Code in einer deklarativen Weise, aber sie wird [nicht mehr als eine Sicherheitsgrenze unterstützt](~/docs/framework/misc/security-transparent-code.md). Diese Funktion wird oft von Silverlight verwendet. 

Verwenden Sie vom Betriebssystem bereitgestellte Sicherheitsgrenzen, wie Virtualisierung, Container oder Benutzerkonten zum Ausführen von Prozessen mit den geringsten Rechten.

## <a name="converting-a-pcl-project"></a>Konvertieren eines PCL-Projekts

Sie können die Ziele des PCL-Projekts auf .NET-Standard konvertieren, indem Sie die Bibliothek in Visual Studio 2017 laden und die folgenden Schritte ausführen:

1. Klicken Sie mit der rechten Maustaste auf die Projektdatei, und klicken Sie auf **Eigenschaften**.
1. Klicken Sie unter **Bibliothek** auf **Ziel: .NET-Plattform (Standard)**.

Wenn Ihre Pakete NuGet 3.0 unterstützen, weist das Projekt .NET-Standard neu zu.

Wenn Ihre Pakete NuGet 3.0 nicht unterstützen, erhalten Sie ein Dialogfeld von Visual Studio, das besagt, dass Sie Ihre aktuellen Pakete deinstallieren sollen. Wenn Sie diesen Hinweis erhalten, führen Sie die folgenden Schritte aus:

1. Klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie auf **NuGet-Pakete verwalten**.
1. Notieren Sie sich die Projektpakete.
1. Deinstallieren Sie die Pakete einzeln.
1. Sie müssen möglicherweise Visual Studio neu starten, um die Deinstallation abzuschließen. Wenn dies der Fall ist, wird Ihnen die Schaltfläche **Neu starten** im Fenster **NuGet-Paket-Manager** angezeigt.
1. Wenn das Projekt erneut geladen wird, ist .NET-Standard das Ziel. Fügen Sie die Pakete hinzu, die Sie deinstallieren mussten.

## <a name="retargeting-your-net-framework-code-to-net-framework-462"></a>Neuzuweisung Ihres .NET Framework-Codes zu .NET Framework 4.6.2

Wenn Ihr Code nicht .NET Framework 4.6.2 als Ziel festlegt, wird empfohlen, dass Sie .NET Framework 4.6.2. neu zuweisen. Dadurch wird die Verfügbarkeit der neuesten API-Alternativen für Fälle sichergestellt, in denen .NET-Standard vorhandene APIs nicht unterstützt.

Führen Sie für jedes Projekt in Visual Studio, das Sie portieren möchten, die folgenden Schritte durch:

1. Klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie auf Eigenschaften.
1. Klicken Sie in der Dropdownliste **Zielframework** auf **.NET Framework 4.6.2**.
1. Kompilieren Sie Ihre Projekte neu.

Da Ihre Projekte jetzt .NET Framework 4.6.2 als Ziel festgelegt haben, verwenden Sie diese Version von .NET Framework als Grundlage zum Portieren von Code.

## <a name="determining-the-portability-of-your-code"></a>Bestimmen der Portabilität Ihres Codes

Führen Sie als nächsten Schritt den API Portability Analyzer (ApiPort) aus, um einen Portabilitätsbericht für die Analyse zu erstellen.

Stellen Sie sicher, dass Sie den [API Portability Analyzer (ApiPort)](../../standard/analyzers/portability-analyzer.md) verstehen und verstehen, wie Sie Portabilitätsberichte generieren, die .NET Core als Ziel festlegen. Wie Sie das bewerkstelligen, hängt von Ihren Bedürfnissen und Ihrem persönlichen Geschmack ab. Nachfolgend werden ein paar unterschiedliche Ansätze aufgeführt. Sie können Schritte dieser Ansätze kombinieren, je nachdem, wie der Code strukturiert ist.

### <a name="dealing-primarily-with-the-compiler"></a>Schwerpunktmäßiger Umgang mit dem Compiler

Diese Vorgehensweise ist möglicherweise am Besten für kleine Projekte oder für Projekte, die nicht viele .NET Framework-APIs verwenden. Der Ansatz ist einfach:

1. Führen Sie optional ApiPort auf Ihrem Projekt aus. Wenn Sie ApiPort ausführen, erhalten Sie Informationen aus dem Bericht über Probleme, die Sie behandeln müssen.
1. Kopieren Sie Ihren gesamten Code in ein neues .NET Core-Projekt.
1. Lösen Sie Compilerfehler, bis das Projekt vollständig kompiliert ist, während Sie auf den Portabilitätsbericht verweisen (wenn er generiert wurde).

Obwohl dieser Ansatz unstrukturiert ist, führt der codeorientierte Ansatz oft dazu, dass Fehler schnell gelöst werden, und er kann sich auch am besten für kleinere Projekte oder Bibliotheken eignen. Ein Projekt, das nur Datenmodelle enthält, kann möglicherweise ein idealer Kandidat für diesen Ansatz sein.

### <a name="staying-on-the-net-framework-until-portability-issues-are-resolved"></a>Auf dem .NET Framework bleiben, bis Portabilitätsprobleme gelöst sind

Dieser Ansatz kann möglicherweise die beste Lösung, wenn Sie lieber über Code verfügen möchten, der während des gesamten Prozesses kompiliert wird. Die Vorgehensweise sieht wie Folgt aus:

1. Führen Sie ApiPort auf einem Projekt aus.
1. Beheben Sie Probleme mithilfe der verschiedenen APIs, die übertragbar sind.
1. Notieren Sie alle Bereiche, in denen Sie daran gehindert werden, eine direkte Alternative zu verwenden.
1. Wiederholen Sie die vorherigen Schritte für alle Projekte, die Sie portieren, bis Sie sicher sind, dass jedes Projekt in ein neues .NET Core-Projekt kopiert wurde.
1. Kopieren Sie den Code in ein neues .NET Core-Projekt.
1. Lösen sie alle Probleme, bei denen Sie sich notiert haben, dass keine direkte Alternative existiert.

Dieser sorgfältige Ansatz ist strukturierter als einfach Compilerfehler zu beheben, ist jedoch auch relativ codeorientiert und hat den Vorteil, dass immer Code vorhanden ist, der kompiliert wird. Die Herangehensweise, wie Sie bestimmte Probleme lösen, die nicht nur durch einfaches Verwenden einer anderen API behoben werden können, variiert stark. Möglicherweise müssen Sie einen umfassenderen Plan für bestimmte Projekte entwickeln, der als weitere Vorgehensweise gilt.

### <a name="developing-a-comprehensive-plan-of-attack"></a>Entwickeln eines umfassenden Vorgehensplans

Dieser Ansatz ist möglicherweise am besten für größere und komplexere Projekte geeignet, bei denen es womöglich nötig ist, Code umzustrukturieren oder bestimmte Bereiche komplett neu zu schreiben, um .NET Core zu unterstützen. Die Vorgehensweise sieht wie Folgt aus:

1. Führen Sie ApiPort auf einem Projekt aus.
1. Sie müssen verstehen, wo jeder nicht portable Typ verwendet wird und wie sich dies auf die gesamte Portabilität auswirkt.
   - Verstehen sie die Natur dieser Typen. Stellen sie nur eine geringe Anzahl dar, werden jedoch oft verwendet? Stellen sie eine hohe Anzahl dar, werden jedoch nicht oft verwendet? Ist ihre Verwendung auf einen Punkt ausgerichtet oder im gesamten Code verteilt?
   - Ist es einfach, Code zu isolieren, der nicht portabel ist, damit Sie effektiver damit umgehen können?
   - Müssen Sie Ihren Code umgestalten?
   - Gibt es für nicht portable Typen alternative APIs, die die gleiche Aufgabe erfüllen? Wenn Sie z.B. die <xref:System.Net.WebClient>-Klasse verwenden, können Sie stattdessen möglicherweise die <xref:System.Net.Http.HttpClient>-Klasse verwenden.
   - Gibt es unterschiedliche portable APIs, die für die Erfüllung der Aufgabe verfügbar sind, auch wenn es kein direkter Ersatz ist? Wenn Sie z.B. <xref:System.Xml.Schema.XmlSchema> verwenden, um XML zu analysieren, aber keine XML-Schemasuche erforderlich ist, können Sie die <xref:System.Xml.Linq>-APIs verwenden und das Analysieren selbst implementieren, anstatt auf eine API zu vertrauen.
1. Wenn Sie über Assemblys verfügen, die schwierig zu portieren sind, bringt es etwas, Sie vorübergehend in .NET Framework zu lassen? Nachfolgend sind einige Dinge aufgeführt, die Sie bedenken sollten:
   - Sie verfügen womöglich über einige Funktionen in Ihrer Bibliothek, die mit .NET Core inkompatibel sind, da es zu sehr auf der bestimmten .NET Framework- oder Windows-Funktionalität basiert. Ist es also vorteilhaft, diese Funktionalität vorübergehend zu ignorieren, und temporär eine .NET Core-Version Ihrer Bibliothek mit weniger Funktionen zu veröffentlichen, bis die Ressourcen verfügbar sind, um die Funktionieren zu portieren?
   - Würde eine Umgestaltung helfen?
1. Ist es sinnvoll, eine eigene Implementierung einer nicht verfügbaren .NET Framework-API zu schreiben?
   Sie könnten kopieren, ändern und Code aus der [.NET Framework Verweisquelle](https://github.com/Microsoft/referencesource) verwenden. Der Quellcode für den Verweis wird unter der [MIT-Lizenz](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt) lizenziert. Daher verfügen Sie über eine erhebliche Freiheit, die Quelle als Grundlage für Ihren eigenen Code zu verwenden. Stellen Sie nur sicher, dass Sie Microsoft ordnungsgemäß Ihrem Code zugeordnet haben.
1. Wiederholen Sie diesen Vorgang für verschiedene Projekte nach Bedarf.
 
Die Analysephase kann je nach Größe Ihrer Codebasis einige Zeit dauern. Sie können sich auf lange Sicht Zeit in dieser Phase sparen, wenn Sie den Umfang der erforderlichen Änderungen verstehen und einen Plan entwickeln, besonders, wenn sie über eine komplexe Codebasis verfügen.

Ihr Plan kann wichtige Änderungen an Ihrer Codebase erfordern, während Sie noch immer auf .NET Framework 4.6.2 abzielen. Dadurch entsteht eine strukturiertere Version des vorherigen Ansatzes. Wie Sie Ihren Plan ausführen, hängt von Ihrer Codebasis ab.

### <a name="mixing-approaches"></a>Mischen von Ansätzen

Es ist wahrscheinlich, dass Sie die oben genannten Vorgehensweisen jeweils pro Projekt mischen werden. Sie sollten den Ansatz wählen, der am meisten Sinn für Sie und Ihre Codebasis macht.

## <a name="porting-your-tests"></a>Portieren der Tests

Die beste Möglichkeit, um sicherzustellen, dass alles funktioniert, wenn Sie Ihren Code importiert haben, ist das Testen Ihres Codes beim Portieren auf .NET Core. Zu diesem Zweck müssen Sie ein Test-Framework verwenden, das Tests für .NET Core erstellt und ausführt. Derzeit stehen Ihnen drei Optionen zur Verfügung:

- [xUnit](https://xunit.github.io/)
  * [Erste Schritte](https://xunit.github.io/docs/getting-started-dotnet-core.html)
  * [Tool zum Konvertieren eines MSTest-Projekts zu xUnit](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [NUnit](https://nunit.org/)
  * [Erste Schritte](https://github.com/nunit/docs/wiki/Installation)
  * [Blogbeitrag zur Migration von MSTest zu NUnit (in englischer Sprache)](https://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [MSTest](https://docs.microsoft.com/visualstudio/test/unit-test-basics)

## <a name="recommended-approach-to-porting"></a>Empfohlener Ansatz zum Portieren

Die Arbeit für die Portierung hängt letztendlich schwer davon ab, wie Ihr .NET Framework-Code strukturiert ist. Eine gute Möglichkeit zum Portieren von Code ist der Beginn mit der *Basis* Ihrer Bibliothek, die aus den grundlegenden Komponenten Ihres Codes besteht. Dies sind womöglich Datenmodelle oder einige andere grundlegende Klassen und Methoden, die von allem anderen direkt oder indirekt verwendet werden.

1. Portieren Sie das Testprojekt, das die Ebene Ihrer Bibliothek testet, die Sie derzeit portieren.
1. Kopieren Sie die Basis Ihrer Bibliothek in ein neues .NET Core-Projekt, und wählen Sie die Version von .NET-Standard aus, die Sie unterstützen möchten.
1. Führen Sie alle erforderlichen Änderungen durch, sodass der Code kompiliert werden kann. Vieles davon erfordert möglicherweise das Hinzufügen von NuGet-Paketabhängigkeiten zu ihrer *csproj*-Datei.
1. Führen Sie die Tests aus, und führen Sie erforderliche Anpassungen durch.
1. Wählen Sie die nächste Codeebene aus, die portiert werden soll, und wiederholen Sie die vorherigen Schritte.

Wenn Sie mit der Basis Ihrer Bibliothek beginnen und sich von der Basis aus nach außen bewegen, und jede Ebene wie erforderlich testen, ist die Portierung ein schematischer Prozess, bei dem Probleme jeweils auf einer Codeebene isoliert werden.
