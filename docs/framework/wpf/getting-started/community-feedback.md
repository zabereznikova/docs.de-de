---
title: Communityressourcen
ms.date: 03/01/2018
helpviewer_keywords:
- community resources [WPF]
- forums [WPF]
- bug descriptions [WPF]
ms.assetid: 468b060a-d54b-4900-a74a-9faccb554045
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e903045195d6f464659876334f7fedc5c695e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733809"
---
# <a name="wpf-community-feedback"></a>WPF-communityfeedback

Microsoft bietet eine Vielzahl von Communityressourcen an, die Sie kennenlernen, erörtern und Feedback zu Windows Presentation Foundation (WPF) geben können. Zu diesen Ressourcen zählen Foren und die [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) -Website. Die einzelnen Communityressourcen bieten unterschiedliche Vorteile. Diese Vorteile werden hier beschrieben, ebenso wie eine Reihe von bewährten Methoden für die Verwendung von, um die beste Antwort von der Community bei groß und Microsoft zu gewährleisten.

> [!NOTE]
> Verwenden Sie nicht den Feedback Abschnitt unten auf jeder Seite, um Produktfeedback zu senden. Diese Links sind nur für das Feedback zur Dokumentation gedacht.

## <a name="forums"></a>Foren

Das [WPF-Forum](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=wpf) ist die primäre Communityressource zur Erörterung und Behebung von Problemen. Foren vereinfachen die Diskussion und Problemlösung, indem sie ein umfassendes Angebot unterstützender Features bereitstellen, die Folgendes umfassen:

- Suchfunktionen
- Verfolgung von Diskussionen
- Umfangreiche Formatierung für Text und Code
- Visual Studio-Integration
- Einbeziehung von MVPs (Most Valued Professionals) und der Community
- Überwachung, um sicherzustellen, dass auf Beiträge schnellstmöglich reagiert wird

Eine weitere Option, mit der Sie Fragen zu WPF an die Community stellen können, finden Sie unter [Stack Overflow](https://stackoverflow.com/questions/tagged/wpf).

### <a name="forum-best-practices"></a>Bewährte Methoden für das Forum

Mithilfe der folgenden bewährten Methoden können Sie Probleme behandeln, die im WPF-Forum zu einem schnellstmöglichen Zeitpunkt gepostet werden. Diese Vorgehensweisen gelten für alle Foren.

#### <a name="search-existing-posts"></a>Vorhandene Beiträge durchsuchen

Einige Probleme treten häufiger auf, sodass andere Benutzer ihnen möglicherweise bereits begegnet sind. Folglich können Sie das Problem schnell lösen oder Ihren Beitrag einer vorhandenen Diskussion hinzufügen.

#### <a name="use-meaningful-titles"></a>Sinnvolle Titel verwenden

Präzise, aussagekräftige Titel verbessern die Auffindbarkeit ihrer Beiträge. Außerdem erleichtern Sie es anderen Mitgliedern der WPF-Forums Community, herauszufinden, ob Sie Ihr Problem lösen können.

#### <a name="include-appropriate-content"></a>Entsprechenden Inhalt einschließen

Beschreiben Sie das Problem, und erfahren Sie, wie Sie versuchen, es zu bearbeiten. Falls möglich, sollten Sie unterstützende Codeausschnitte oder ein möglichst einfaches Beispiel hinzufügen, das Ihr Problem veranschaulicht. Diese Einzelheiten erhöhen die Chance, dass Ihre Frage rasch beantwortet wird.

## <a name="visual-studio-developer-community"></a>Visual Studio Developer Community

Mitunter lassen sich Probleme nur schwierig oder gar nicht beheben. Ursache solcher Situationen können Probleme in der Technologie, Schwierigkeiten der Anwendung der Technologie auf bestimmte Szenarien oder eine mangelnde Unterstützung bestimmter Szenarien sein. Diese Informationen sind für Microsoft von Bedeutung und können über die [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) -Website bereitgestellt werden.

Elemente, die im WPF-Produkt Feedback Center gepostet werden, werden an die interne Fehlerdatenbank des WPF-Teams weitergeleitet. Folglich ist es die zuverlässigste Möglichkeit, Ihr Feedback an den Besitzer der WPF-Funktion zu senden. Darüber hinaus können Sie Vorschläge und Fehler überprüfen und nachverfolgen sowie darauf abstimmen, was dem WPF-Team hilft, Probleme zu priorisieren.

### <a name="developer-community-best-practices"></a>Bewährte Methoden für die Entwickler Community

Beim Veröffentlichen in der Visual Studio-Entwickler Community sind die Durchsuchen vorhandener Beiträge, die Bereitstellung eines aussagekräftigen Titels und der entsprechenden Inhalte wichtig, ebenso wie für die Bereitstellung im WPF-Forum. Die folgenden bewährten Vorgehensweisen werden zusätzlich empfohlen.

#### <a name="search-existing-posts"></a>Vorhandene Beiträge durchsuchen

Einige Probleme treten häufiger auf, sodass andere Benutzer ihnen möglicherweise bereits begegnet sind. Folglich können Sie das Problem schnell lösen, oder Sie können die Eingabe einem vorhandenen Problem hinzufügen.

#### <a name="use-meaningful-titles"></a>Sinnvolle Titel verwenden

Präzise, aussagekräftige Titel erhöhen die Wahrscheinlichkeit, dass Ihr Problem in kürzester Zeit an das am besten geeignete WPF-Team weitergeleitet wird. Dies ist besonders wichtig für eine Technologie wie WPF, die viele interverwandte Funktionen enthält.

#### <a name="describe-how-to-reproduce-your-bug"></a>Beschreiben, wie Sie Ihren Fehler reproduzieren

Wenn Sie einen Fehler melden, müssen Sie die folgenden Angaben machen, sofern relevant:

- Geben Sie eine klare Beschreibung des Fehlers.
- Fügen Sie Codeausschnitte hinzu, um die Fehlerbeschreibung zu ergänzen.
- Listen Sie die Schritte auf, die veranschaulichen, wie sich der Fehler reproduzieren lässt.
- Schließen Sie ein möglichst kleines Codebeispiel ein, mit dem der Fehler reproduziert wird.
- Geben Sie an, ob sich der Fehler durchgängig reproduzieren lässt oder nicht.
- Fügen Sie relevante Ausnahmeinformationen hinzu.

 Wenn der Fehler im Zusammenhang mit der Installation oder dem Setup steht, fügen Sie die relevanten Installationsprotokolle und Momentaufnahmen an (Dateien mit dem Präfix „dd_“, die sich im Ordner %temp% befinden).

 Bei Kompilierungs- oder Buildproblemen fügen Sie die Buildprotokolle an. Das MSBuild-System kann so konfiguriert werden, dass die Protokollierung mit verschiedenen ausführlichkeiten unterstützt wird, indem der Schalter/v: von der Befehlszeile aus oder durch Konfigurieren der entsprechenden Ebene aus einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio verwendet wird.

#### <a name="provide-environment-information"></a>Bereitstellen von Umgebungs Informationen

Hintergrundinformationen können oft nützlich sein, um Ihren Beitrag mit Kontext zu versehen. Erwähnen Sie insbesondere die Betriebssystem Plattform, die Prozessorfamilie und die Architektur, z. b. "Windows 10-Version 1709, Intel (r) Xeon (r), x64".

Wenn sich das Problem, das Sie melden, auf das Rendering bezieht, sollten Sie nach Möglichkeit auch Angaben zu Grafikkarte und Treiber machen. Diese Informationen sind wichtig, da es sich bei WPF um ein Präsentations Framework handelt.

#### <a name="provide-solution-or-project-information"></a>Lösungs-oder Projektinformationen bereitstellen

Fehler können auf zur Entwicklung und Erstellung von Anwendungen verwendete Tools und die zu erstellenden Anwendungstypen bezogen sein. Daher können folgende Angaben nützlich sein:

- Der Typ der Anwendung, den Sie erstellen, z. B.:
  - Anwendung ( *. exe*) oder Bibliothek ( *. dll*)
  - Extensible Application Markup Language (XAML) Browser Anwendung (XBAP)
  - Lose XAML-Anwendung
  - Eigenständige installierte Anwendungen
  - Eigenständige ClickOnce-bereitgestellte Anwendungen
- Das Entwicklungstool, z. B.:
  - MSBuild
  - Ausdrucks Grafik-Designer
  - Ausdrucks interaktiver Designer
  - öffnen
- Die Projektmappenkonfiguration, z. B.:
  - Eine Lösung
  - Ein einzelnes Projekt
  - Eine Lösung mit mehreren abhängigen Projekten
- Hat die Anwendung sprachspezifische oder sprachunabhängige Ressourcen? Haben Sie beispielsweise die `UICulture`-Projekteigenschaft oder lokalisierbare Metadaten für `Application`-, `Page`- und `Resource`-Typen angegeben?
- Haben Sie die neutrale Spracheinstellung in der Datei „AssemblyInfo.cs“ oder „AssemblyInfo.vb“ verwendet?

#### <a name="provide-scenario-and-impact-information"></a>Informationen zu Szenario und Auswirkung bereitstellen

Geben Sie Informationen zum Szenario an, in dem der Fehler und seine Auswirkung angezeigt werden. Diese Informationen sind für das WPF-Team äußerst wichtig, wenn es entscheidet, wann und wie ein Problem behoben werden soll oder ob stattdessen eine akzeptable Problem Umgehung verwendet werden kann.

In der Regel haben mit Absturz und Datenverlust einhergehende Szenarien große Auswirkungen und können daher am leichtesten priorisiert werden. Einige Fehler treten jedoch nur in ungewöhnlichen Szenarien auf, die in einigen Fällen auch Hauptszenarien sein können. Durch die Bereitstellung eines Kontexts für Szenario und Auswirkung kann das WPF-Team die richtige Entscheidung treffen.

## <a name="see-also"></a>Siehe auch

- [Melden eines Problems mit Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)
