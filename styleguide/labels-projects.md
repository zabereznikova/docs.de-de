---
ms.openlocfilehash: 394ed636cece766d61b1a10403b98c73f1d3cb93
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041260"
---
# <a name="labels-and-projects-roadmap"></a>Roadmap für Bezeichnungen und Projekte

Das Team für .NET-Dokumentationen nutzt häufig [GitHub-Bezeichnungen](https://github.com/dotnet/docs/labels) zum Organisieren der Arbeit. Durch das Filtern nach Bezeichnungen können wir uns auf der Website für [.NET-Dokumentationen](https://docs.microsoft.com/dotnet) schnell auf interessante Bereiche konzentrieren. 

Außerdem verwenden wir auch [GitHub-Projekte](https://github.com/dotnet/docs/projects), um Sprints und andere zielorientierte Epics zu organisieren.

Diese Roadmap erläutert, wie wir diese Organisationstools verwenden und enthält Links zu praktischen Filtern, die wir verwenden, um relevante Bereiche zu finden.

## <a name="labels"></a>Bezeichnungen

Wenn Sie zum ersten Mal etwas zu [dotnet/docs](https://github.com/dotnet/docs) beitragen, sollten Sie mit den [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs)-Issues beginnen. Dabei handelt es sich um Issues, die sich stärker auf einen Bereich konzentrieren. Sie eignen sich besonders für Ihren ersten Beitrag. In der Ansicht „up-for-grabs“ können Sie basierend auf Bereich und Priorität nach Issues filtern. Mithilfe von [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) konnten wir Issues identifizieren, die sich für Anfänger eignen und mit denen Sie Ihren ersten kleinen Beitrag leisten können.

Wir verwenden Bezeichnungen, um Issues auf verschiedene Art und Weise zu klassifizieren:

- [.NET-Leitfäden](#find-a-single-net-guide) und [Abschnitte eines Leitfadens](#search-one-section-of-a-guide)
- [Zielrelease](#releases)
- [Priority](#priority)

Sie können eine Bezeichnung aus jedem Bereich kombinieren (guide, release, priority), um genau die Issues zu finden, an denen Sie arbeiten möchten.

### <a name="find-a-single-net-guide"></a>Suchen nach einzelnem .NET-Leitfaden

Wir verwenden Bezeichnungen für die einzelnen Architektur-E-Books und für jeden .NET-Leitfaden. 

![:book: Leitfaden auf hellgrünem Hintergrund](./images/guide.png "Präfix für Architekturleitfadenbezeichnungen")

Architektur-E-Books enthalten das Präfix `:book: guide` und weisen einen hellgrünen Hintergrund auf. Dies sind die langen Bereiche , die empfohlene Architektur abdecken. Hier werden aktuelle Issues für die einzelnen .NET-Architekturleitfäden gefiltert.

- [ASP.NET Core-Web-Apps](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [Blazor](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [Cloud Native](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [Docker-Lebenszyklus](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [gRPC](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [Modernisieren von w/ Windows-Containern](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [.NET-Microservices](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [Serverlose Apps](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

Diese Bezeichnung wird auch für die [Framework-Entwurfsrichtlinien](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines) angewendet. Dieser Bereich weist das gleiche Bezeichnungsdesign auf, Community-PRs wird davon aber abgeraten. Dies ist mit der Berechtigung neu gedrucktes Material und sollte nicht bearbeitet werden.

![:books: Bereich auf dunkelblauem Hintergrund](./images/area.png "Präfix für .NET-Leitfadenbereichsbezeichnungen")

Jeder .NET-Leitfaden ist mit dem Präfix `:books: Area` versehen und weist einen dunkelblauen Hintergrund auf. Hier werden aktuelle Issues für die einzelnen .NET-Leitfäden gefiltert.

- [API-Referenz](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [Azure .NET SDK](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [Leitfaden für C#](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [Desktopleitfaden](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [Leitfaden für F#](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [Leitfaden für ML.NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- [.NET-Architekturleitfaden:](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) Kann entfernt werden
- [Leitfaden für .NET Core](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [Leitfaden für .NET für Apache Spark](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [Leitfaden für .NET Framework](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [.NET Guide (Leitfaden für .NET)](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- [Roslyn-API-Referenz:](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) Kann entfernt werden
- [Leitfaden für Visual Basic](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a>Durchsuchen eines Abschnitts eines Leitfadens

![:card_file_box: Bereich auf mittelblauem Hintergrund](./images/technology.png "Präfix für Unterbereichbezeichnungen in .NET-Leitfäden")

Die .NET-Leitfäden sind groß, sodass diese Bezeichnungen den Bereich durch einen Abschnitt eines Leitfadens weiter einschränken. Jeder Unterbereich eines .NET-Leitfadens ist mit dem Präfix `:card_file_box: Technology` versehen und weist einen mittelblauen Hintergrund auf. Viele dieser Bezeichnungen gelten für mehrere Leitfäden, während andere in nur einem Leitfaden aufgeführt sind. Fügen Sie nach dem Filtern nach einem Bereich eine dieser Bezeichnungen hinzu, um den Umfang des Issues weiter einzuschränken.

- AppCompat
- asynchrone Aufgabe
- erweiterte C#-Konzepte
- C#-Compiler
- C#-Grundlagen
- Erste Schritte mit C#
- C#-Programmiersprachenreferenz
- C# Null-Sicherheit
- Neuerungen in C#
- CLI
- Datenzugriff
- Docker
- Installer
- LINQ
- NCL
- .NET-Standard
- Roslyn-APIs
- Sicherheit
- WCF
- WF
- WIF
- WinForms
- WPF

### <a name="releases"></a>Versionen

![:checkered_flag: Release: auf dunkelgelbem Hintergrund](./images/release.png "Präfix für Releasebezeichnungen")

Issues, die für ein bestimmtes Release gekennzeichnet sind, werden mit dem Präfix `:checkered_flag: Release:` versehen und weisen einen dunkelgelben Hintergrund auf. 

- .NET Core 2.2
- .NET Core 3.0

### <a name="priority"></a>Priorität

Bei Prioritätsbezeichnungen folgt auf `P` eine einzelne Ziffer. Niedrigere Zahlen stehen für eine höhere Priorität.

- P0
- P1
- P2

### <a name="what-about-the-other-labels"></a>Welche Funktion haben die anderen Bezeichnungen?

Es gibt viele andere Bezeichnungen, die von den Inhaltsteams verwendet werden, um unterschiedliche Klassifizierungen von Issues zu verwalten. Wenn Sie nicht Teil des Inhaltsteams sind, können Sie diese anderen Bezeichnungen ignorieren.

## <a name="projects"></a>Projekte

Mitwirkende sollten die [Projekte für .NET-Communitymitarbeiter](https://github.com/dotnet/docs/projects/35) überprüfen. Wir haben verschiedene Spalten für die Wartung, das Aktualisieren von Dokumenten und neue Inhaltsaufgaben erstellt. Auf diese Weise kann nach relevanten Aufgaben gesucht werden. (Beachten Sie, dass die Projektansicht mithilfe der oben beschriebenen Bezeichnungen gefiltert werden kann.) 

Projekte werden auch auf zwei verschiedene Arten verwendet:

- Projekttypen „Monat JJJJ“: Dabei handelt es sich um Scrum-Boards für den Arbeitsplan jedes Monats.
- Lange Epics: Diese werden verwendet, um Aufgaben für ein Ziel zu organisieren, wenn sich die Arbeit über mehrere Monate erstreckt.
