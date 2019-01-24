---
title: WPF-Communityfeedback
ms.date: 03/01/2018
helpviewer_keywords:
- community resources [WPF]
- forums [WPF]
- bug descriptions [WPF]
ms.assetid: 468b060a-d54b-4900-a74a-9faccb554045
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f77058ac0cb87d0316395bce1dfb11401a2ce806
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585340"
---
# <a name="wpf-community-feedback"></a>WPF-Communityfeedback

Microsoft stellt eine Vielzahl von Communityressourcen für Sie erfahren, diskutieren und Ihr Feedback auf der Windows Presentation Foundation (WPF). Zu diesen Ressourcen gehören, Foren und [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) Standort. Die einzelnen Communityressourcen bieten unterschiedliche Vorteile. Diese Vorteile werden hier beschrieben, wie ein Satz von best Practices für die Verwendung der einzelnen insbesondere die beste Antwort von der Community insgesamt und Microsoft sicher.

> [!NOTE]
> Verwenden Sie am unteren Rand jeder Seite im Feedbackbereich nicht zum Senden von Feedback zu Produkten an. Diese Links sind nur für das Feedback zur Dokumentation gedacht.

## <a name="forums"></a>Foren

Die [WPF-Forum](https://social.msdn.microsoft.com/Forums/vstudio/en-US/home?forum=wpf) ist die primäre Communityressource zur Diskussion und Behebung von Problemen. Foren vereinfachen die Diskussion und Problemlösung, indem sie ein umfassendes Angebot unterstützender Features bereitstellen, die Folgendes umfassen:

- Suchfunktionen
- Verfolgung von Diskussionen
- Umfangreiche Formatierung für Text und Code
- Visual Studio-Integration
- Einbeziehung von MVPs (Most Valued Professionals) und der Community
- Überwachung, um sicherzustellen, dass auf Beiträge schnellstmöglich reagiert wird

Eine weitere Option für Sie zu WPF für die Community Fragen ist [Stack Overflow](https://stackoverflow.com/questions/tagged/wpf).

### <a name="forum-best-practices"></a>Bewährte Vorgehensweisen in Foren

Mithilfe der folgenden bewährten Methoden Hilfe, um Probleme im WPF-Forum im schnellstmöglich gepostet. Diese Vorgehensweisen gelten für alle Foren.

#### <a name="search-existing-posts"></a>Durchsuchen vorhandener Beiträge

Einige Probleme treten häufiger auf, sodass andere Benutzer ihnen möglicherweise bereits begegnet sind. Folglich können Sie das Problem schnell lösen oder Ihren Beitrag einer vorhandenen Diskussion hinzufügen.

#### <a name="use-meaningful-titles"></a>Verwenden aussagekräftiger Titel

Präzise, aussagekräftige Titel verbessern die Auffindbarkeit der Beiträge. Sie erleichtern auch für andere Mitglieder der WPF-Forum-Community zu bestimmen, ob sie Ihr Problem lösen können.

#### <a name="include-appropriate-content"></a>Schließen geeigneter Inhalte ein

Beschreiben Sie das Problem und wie Sie versucht haben, um diesen durchgearbeitet haben. Falls möglich, sollten Sie unterstützende Codeausschnitte oder ein möglichst einfaches Beispiel hinzufügen, das Ihr Problem veranschaulicht. Diese Einzelheiten erhöhen die Chance, dass Ihre Frage rasch beantwortet wird.

## <a name="visual-studio-developer-community"></a>Visual Studio-Entwicklercommunity

Mitunter lassen sich Probleme nur schwierig oder gar nicht beheben. Ursache solcher Situationen können Probleme in der Technologie, Schwierigkeiten der Anwendung der Technologie auf bestimmte Szenarien oder eine mangelnde Unterstützung bestimmter Szenarien sein. Diese Informationen ist wichtig, Microsoft und kann bereitgestellt werden, über die [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) Standort.

Auf der WPF-Produktfeedbackcenter werden an die interne Fehlerdatenbank des WPF-Teams weitergeleitet. Daher ist es die zuverlässigste Möglichkeit, um Ihr Feedback an dem Besitzer der WPF-Funktion zu erhalten. Darüber hinaus können Sie überprüfen und nachverfolgen, Empfehlungen und Fehler sowie dafür stimmen, wodurch die WPF-Team Probleme priorisieren.

### <a name="developer-community-best-practices"></a>Best Practices der Entwickler-Community

Bereitstellen in der Visual Studio Developer Community Durchsuchen vorhandener Beiträge, Angabe eines aussagekräftigen Titels und geeignete Inhalte sind wichtige bewährte Vorgehensweisen nur als auch für das Senden an die WPF-Forum. Die folgenden bewährten Vorgehensweisen werden zusätzlich empfohlen.

#### <a name="search-existing-posts"></a>Durchsuchen vorhandener Beiträge

Einige Probleme treten häufiger auf, sodass andere Benutzer ihnen möglicherweise bereits begegnet sind. Daher können Sie das Problem schnell lösen, oder Sie können die Eingabe ein vorhandenes Problem hinzufügen.

#### <a name="use-meaningful-titles"></a>Verwenden aussagekräftiger Titel

Präzise, aussagekräftige Titel verbessern Sie die Wahrscheinlichkeit, dass Ihr Problem in kürzestmöglicher Zeit an das am besten geeigneten WPF-Team weitergeleitet wird. Dies ist besonders wichtig für eine Technologie wie WPF, die viele zusammenhängende Features enthält.

#### <a name="describe-how-to-reproduce-your-bug"></a>Beschreibt die Reproduktion Ihres Fehlers

Wenn Sie einen Fehler melden, müssen Sie die folgenden Angaben machen, sofern relevant:

- Geben Sie eine klare Beschreibung des Fehlers.
- Fügen Sie Codeausschnitte hinzu, um die Fehlerbeschreibung zu ergänzen.
- Listen Sie die Schritte auf, die veranschaulichen, wie sich der Fehler reproduzieren lässt.
- Schließen Sie ein möglichst kleines Codebeispiel ein, mit dem der Fehler reproduziert wird.
- Geben Sie an, ob sich der Fehler durchgängig reproduzieren lässt oder nicht.
- Fügen Sie relevante Ausnahmeinformationen hinzu.

 Wenn der Fehler im Zusammenhang mit der Installation oder dem Setup steht, fügen Sie die relevanten Installationsprotokolle und Momentaufnahmen an (Dateien mit dem Präfix „dd_“, die sich im Ordner %temp% befinden).

 Bei Kompilierungs- oder Buildproblemen fügen Sie die Buildprotokolle an. MSBuild, die System werden, um konfiguriert kann unterstützt Protokollierung mit verschiedenen Ausführlichkeitsgraden, mit dem Schalter "/ v:" über die Befehlszeile oder durch Konfigurieren der entsprechenden Ebene aus einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio.

#### <a name="provide-environment-information"></a>Bereitstellen von Umgebungsinformationen

Hintergrundinformationen können oft nützlich sein, um Ihren Beitrag mit Kontext zu versehen. Erwähnen Sie insbesondere die Betriebssystemplattform, Prozessorfamilie und Architektur, wie z. B. "Windows 10 Version 1709 Intel(R) Xeon(R), X64".

Wenn sich das Problem, das Sie melden, auf das Rendering bezieht, sollten Sie nach Möglichkeit auch Angaben zu Grafikkarte und Treiber machen. Diese Informationen sind wichtig, da WPF ein Präsentationsframework ist.

#### <a name="provide-solution-or-project-information"></a>Geben Sie die Projektmappe oder das Projekt Informationen

Fehler können auf zur Entwicklung und Erstellung von Anwendungen verwendete Tools und die zu erstellenden Anwendungstypen bezogen sein. Daher können folgende Angaben nützlich sein:

- Der Typ der Anwendung, den Sie erstellen, z. B.:
  - Anwendung (*.exe*) oder Bibliothek (*DLL*)
  - Extensible Application Markup Language (XAML)-Browseranwendung (XBAP)
  - Loose XAML-Anwendung
  - Eigenständige installierte Anwendungen
  - Eigenständige mit ClickOnce bereitgestellte Anwendungen
- Das Entwicklungstool, z. B.:
  - MSBuild
  - Expression Graphic Designer
  - Expression Interactive Designer
  - Visual Studio
- Die Projektmappenkonfiguration, z. B.:
  - Eine Lösung
  - Ein einzelnes Projekt
  - Eine Lösung mit mehreren abhängigen Projekten
- Hat die Anwendung sprachspezifische oder sprachunabhängige Ressourcen? Haben Sie beispielsweise die `UICulture`-Projekteigenschaft oder lokalisierbare Metadaten für `Application`-, `Page`- und `Resource`-Typen angegeben?
- Haben Sie die neutrale Spracheinstellung in der Datei „AssemblyInfo.cs“ oder „AssemblyInfo.vb“ verwendet?

#### <a name="provide-scenario-and-impact-information"></a>Geben Sie Informationen zu Szenario und Auswirkungen

Geben Sie Informationen zu diesem Szenario, das den Fehler die Auswirkungen sowie. Diese Informationen sind sehr wichtig für das WPF-Team, wenn sie entscheidet, wann und wie ein Problem behoben werden sollte, oder gibt an, ob eine akzeptable problemumgehung kann stattdessen verwendet werden.

In der Regel haben mit Absturz und Datenverlust einhergehende Szenarien große Auswirkungen und können daher am leichtesten priorisiert werden. Einige Fehler treten jedoch nur in ungewöhnlichen Szenarien auf, die in einigen Fällen auch Hauptszenarien sein können. Bereitstellen von Kontext rund um das Szenario und die Auswirkungen, unterstützt das WPF-Team, das die richtige Entscheidung treffen.

## <a name="see-also"></a>Siehe auch

- [Melden eines Problems mit Visual Studio 2017](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)
