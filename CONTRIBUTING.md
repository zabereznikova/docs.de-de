---
ms.openlocfilehash: e5da9a98e8725880223df3737dc60f773db8d20e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79141132"
---
# <a name="contributing"></a>Beitragen

Vielen Dank für Ihr Interesse und Ihre Bereitschaft, an der .NET-Dokumentation mitzuwirken!

> Wir befassen uns derzeit damit, unsere Richtlinien in ein websiteweites Mitwirkungshandbuch zu überführen.
> Besuchen Sie die Seite [Leitfaden für Mitwirkende an der Microsoft-Dokumentation: Übersicht](https://docs.microsoft.com/contribute/), um sich den neuen Leitfaden anzuschauen.

Das Dokument beschreibt den Prozess bei der Mitwirkung an den Artikeln und Codebeispielen, die auf der Website [.NET-Dokumentation](https://docs.microsoft.com/dotnet) gehostet werden. Die Beiträge können so einfach wie das Korrigieren von Tippfehlern oder so komplex wie das Verfassen neuer Artikel sein.

- [Verhaltensregeln](#dos-and-donts)
- [Mitwirkungsprozess](#process-for-contributing)
- [Die interaktive C#-Umgebung](#the-c-interactive-experience)
- [Lizenzvereinbarung für Mitwirkende](#contributor-license-agreement)

Dieses Repository enthält die konzeptionelle Dokumentation zu .NET. Die Website „.NET-Dokumentation“ besteht neben diesem Repository aus den folgenden Repositorys:

- [Codebeispiele und -ausschnitte](https://github.com/dotnet/samples): Probleme und Aufgaben für dieses Repository werden in [dotnet/docs/issues](https://github.com/dotnet/docs/issues) nachverfolgt.
- [.NET-API-Referenz](https://github.com/dotnet/dotnet-api-docs): Probleme und Aufgaben für dieses Repository werden in [dotnet/dotnet-api-docs/issues](https://github.com/dotnet/dotnet-api-docs/issues) nachverfolgt.
- [.NET Compiler Platform SDK-Referenz](https://github.com/dotnet/roslyn-api-docs): Probleme und Aufgaben für dieses Repository werden in [dotnet/docs/issues](https://github.com/dotnet/docs/issues) nachverfolgt.

### <a name="contributing-to-international-content"></a>Beitragen zu internationalen Inhalten

Beiträge zu maschinell übersetzten Inhalten (MT) werden derzeit nicht akzeptiert. Um die Qualität von MT-Inhalten zu verbessern, haben wir auf eine neuronale MT-Engine umgestellt. Wir akzeptieren und begrüßen Beiträge zu von Menschen übersetzten Inhalten (Human Translated Content – HT-Inhalte), die zum Trainieren der neuronalen MT-Engine verwendet werden. Im Laufe der Zeit werden Beiträge zum HT-Inhalt somit die Qualität von HT und MT verbessern. Bei MT-Themen wird ein Haftungsausschluss angezeigt, der besagt, dass ein Teil des Themas möglicherweise maschinell übersetzt wurde. Ferner wird die Schaltfläche **Bearbeiten** nicht angezeigt, da sie deaktiviert ist.

## <a name="dos-and-donts"></a>Verhaltensregeln

Die folgende Liste enthält einige grundlegende Regeln, die Sie beachten sollten, wenn Sie an der .NET-Dokumentation mitwirken:

- **NEIN**: Überfallen Sie uns nicht mit großen Pull Requests. Eröffnen Sie stattdessen ein Ticket, und starten Sie eine Diskussion, damit wir uns auf eine Richtung einigen können, bevor Sie sehr viel Zeit investieren. Teilen Sie die Arbeit bei Massenänderungen in kleinere PRs auf (bis zu 100 Dateien). Diese Richtlinie wird dringend empfohlen, wenn Ihr PR die folgenden Richtlinien nicht erfüllt.
- **JA:** Sehen Sie sich die aktuellen [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs)-Issues für Vorschläge zu den Aufgaben an.
- **JA:** Erstellen Sie einen PR für jede Aufgabe. PRs, die mehrere nicht zusammenhängende Änderungen enthalten, sind viel schwieriger zu überprüfen. Dies verzögert die Überprüfung und Zusammenführung von PRS. Diese Richtlinie gilt auch für Überprüfungen: Wir versuchen, nicht zusammenhängenden Änderungen in Überprüfungen nicht vorzuschlagen. Diese Richtlinie gilt es auch bei Communityüberprüfungen zu beachten.
- **JA:** Bieten Sie eine klare Beschreibung der Arbeit in Ihrem PR. Teilen Sie uns mit, was Sie verändert haben und warum. Die Standardbeschreibung „update article.md“ ist für die Prüfer nicht hilfreich.
- **NEIN:** Übermitteln Sie keine PRs für reine Stiländerungen ohne vorherige Erörterung. Für die Überprüfung auf Genauigkeit dieser PRs wird zusätzliche Zeit benötigt, und die Zusammenführung führt häufig zu Zusammenführungskonflikten mit anderen wichtigen Updates. Wir arbeiten daran, einen konsistenten Stil zu befolgen, allerdings gestaltet sich dies durch die vielen verschiedenen Aufgaben schwierig. Wenn aus anderen Gründen wichtige Updates vorgenommen werden, werden diese Artikel vereinheitlicht.
- **JA** Lesen Sie den [Styleguide](./styleguide/template.md) und die Richtlinien bezüglich [Sprache und Schreibstil](./styleguide/voice-tone.md). Neue Ergänzungen sollten diese Richtlinien einhalten.
- **JA** Erstellen Sie einen separaten Branch in Ihrer Verzweigung, bevor Sie an den Artikeln arbeiten.
- **JA** Folgen Sie dem [GitHub-Flow-Workflow](https://guides.github.com/introduction/flow/).
- **JA** Schreiben Sie häufig Blogs und Tweets (oder was auch immer) über Ihre Beiträge!

Diese Richtlinien helfen uns dabei, die kostbare Zeit der Benutzer zu berücksichtigen. Viele tragen zu diesen Repositorys bei. Das Befolgen dieser Richtlinien erleichtert uns das schnelle Überprüfen und Zusammenführen Ihrer PRs. Diese Vorgehensweisen minimieren Konflikte mit PRs von anderen Communitymitgliedern und unserem Team. Da PRs, die diese Richtlinien nicht befolgen, häufig zusätzliche Arbeit für uns und Communitymitglieder verursachen, werden diese möglicherweise abgelehnt. Beginnen Sie mit dem Erstellen eines Issues, wenn Sie eine Ausnahme erstellen möchten.

> Hinweis: Sie werden feststellen, dass sich derzeit einige der Themen nicht nach allen hier und im [Styleguide](./styleguide/template.md) definierten Richtlinien richten. Wir arbeiten daran, auf der gesamten Website Konsistenz zu erzielen.

## <a name="process-for-contributing"></a>Mitwirkungsprozess

Sie benötigen Grundkenntnisse von [Git und GitHub.com](https://guides.github.com/activities/hello-world/).

**Schritt 1:** Überspringen Sie diesen Schritt, wenn Sie nur kleine Änderungen vornehmen möchten (wenn Sie beispielsweise einen Tippfehler korrigieren oder sofort einen Pull Request öffnen, um ein Problem zu beheben, das Sie in der Dokumentation finden). Wenn Sie daran interessiert sind, neue Inhalte zu schreiben oder vorhandene Inhalte sorgfältig zu überarbeiten, eröffnen Sie ein [Ticket](https://github.com/dotnet/docs/issues) (Issue), in dem Sie beschreiben, was Sie tun möchten.
Der Inhalt im Ordner *docs* ist in Abschnitte unterteilt, die sich im Inhaltsverzeichnis (Table of Contents, TOC) wiederfinden. Definieren Sie, an welcher Stelle sich das Thema im Inhaltsverzeichnis befinden wird. Warten Sie auf Feedback zu Ihrem Vorschlag.

- oder -

Sie können auch eins der vorhandenen Tickets auswählen, für die Community-Beiträge willkommen sind. Unter [Projects for .NET Community contributors](https://github.com/dotnet/docs/projects/35) (Projekte für .NET-Community-Mitwirkende) sind viele der Arbeitsaufgaben aufgelistet, die für Community-Mitwirkende verfügbar sind. Je nach Interesse und Engagement können Sie Tickets in den folgenden Kategorien auswählen:

- **Wartung**. Diese Kategorie enthält recht einfache Beiträge, wie z. B. Korrigieren unterbrochener oder fehlerhafter Links, Hinzufügen fehlender Codebeispiele oder Beheben von Problemen mit eingeschränkten Inhalten. In einigen Fällen können sich diese Probleme auf eine große Anzahl von Dateien beziehen. In diesem Fall sollten Sie uns vor Arbeitsbeginn wissen lassen, woran Sie arbeiten möchten.

- **Inhaltsaktualisierungen**. Angesichts des ungeheuren Ausmaßes des Dokumentationssatzes veralten Inhalte schnell und müssen überprüft werden. Darüber hinaus treten einige Inhalte aus verschiedenen Gründen doppelt oder dreifach auf. Beim Aktualisieren von Inhalten muss sichergestellt werden, dass einzelne Themen aktuell sind oder die Inhalte in einem bestimmten Funktionsbereich überprüft werden, um Duplikate zu entfernen und zu gewährleisten, dass in dem kleineren Dokumentationssatz alle eindeutigen Inhalte erhalten bleiben.

- **Erstellen neuer Inhalte**. Wenn Sie an der Erstellung eines eigenen Themas interessiert sind, werden unter diesen Tickets auch Themen aufgelistet, die wir gerne zu unserem Dokumentationssatz hinzufügen möchten. Informieren Sie uns trotzdem bitte, bevor Sie mit der Arbeit an einem Thema beginnen. Wenn Sie über ein Thema schreiben möchten, das hier nicht aufgeführt ist, eröffnen Sie ein Ticket.

Sie können sich auch die Liste [open issues](https://github.com/dotnet/docs/issues) (offene Tickets) anschauen und die Bearbeitung eines Tickets anbieten, das Sie interessiert. Wir verwenden die Bezeichnung [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) (zu haben), um Tickets zu kennzeichnen, bei denen eine Mitwirkung möglich ist.

**Schritt 2:** Verzweigen Sie bei Bedarf das Repository `dotnet/docs`, `dotnet/samples` oder `dotnet/dotnet-api-docs`, und erstellen Sie einen Branch für Ihre Änderungen.

Bei kleinen Änderungen können Sie die Weboberfläche von GitHub verwenden. Klicken Sie einfach bei der Datei, die Sie ändern möchten, auf **Edit the file in your fork of this project** (Datei in Ihrem Branch des Projekts bearbeiten). GitHub erstellt den neuen Branch für Sie, wenn Sie die Änderungen übermitteln.

**Schritt 3:** Nehmen Sie die Änderungen in diesem neuen Branch vor.

Wenn es sich um ein neues Thema handelt, können Sie diese [Vorlagendatei](./styleguide/template.md) als Ausgangspunkt verwenden. Sie enthält die Richtlinien zum Schreiben und erläutert auch die Metadaten, die für jeden Artikel erforderlich sind (z. B. Informationen zum Autor).

Navigieren Sie zu dem Ordner, welcher der Stelle im Inhaltsverzeichnis entspricht, die Sie in Schritt 1 für Ihren Artikel festgelegt haben.
Dieser Ordner enthält die Markdowndateien für alle Artikel in diesem Abschnitt.
Erstellen Sie ggf. einen neuen Ordner für die Dateien mit Ihrem Inhalt. Der Hauptartikel für diesen Bereich wird als *index.md* bezeichnet.
Erstellen Sie in dem Ordner mit Ihrem Artikel für Bilder und andere statische Ressourcen einen Unterordner namens *media* (falls dieser nicht bereits vorhanden ist). Erstellen Sie im Ordner *media* einen Unterordner mit dem Artikelnamen (mit Ausnahme der Indexdatei).
Stellen Sie im Stammverzeichnis des Repositorys im Ordner *samples* größere Beispiele bereit.

Achten Sie darauf, die richtige Markdownsyntax einzuhalten. Weitere Informationen finden Sie im [Styleguide](./styleguide/template.md).

### <a name="example-structure"></a>Beispielstruktur

```
docs
  /about
  /core
    /porting
      porting-overview.md
      /media
        /porting-overview
            portability_report.png
```

**Schritt 4:** Übermitteln Sie einen Pull Request (PR) von Ihrem Branch an `dotnet/docs/master`, `dotnet/dotnet-api-docs/master` oder `dotnet/samples/master`.

Ihr PR sollte *immer* auf den Standardbranch des Repositorys abzielen (es sei denn, Sie arbeiten an einem Releasebranch). Für dotnet/docs ist der Masterbranch der Standardbranch. Für lokalisierte Repositorys ist der Livebranch der Standardbranch. Sie sollten *niemals* einen PR öffnen, der den Livebranch zum Ziel hat.

Jeder PR sollte sich in der Regel auf jeweils ein Ticket beziehen. Mit dem PR können auch mehrere Dateien geändert werden. Wenn Sie sich mit mehreren Korrekturen an verschiedenen Dateien befassen, werden separate PRs bevorzugt.

Wenn sich Ihr PR auf ein vorhandenes Ticket bezieht, fügen Sie der Commit-Nachricht oder PR-Beschreibung das Schlüsselwort `Fixes #Issue_Number` hinzu. Auf diese Weise wird das Ticket automatisch geschlossen, wenn der Pull Request zusammengeführt wird. Weitere Informationen finden Sie unter [Closing issues via commit messages](https://help.github.com/articles/closing-issues-via-commit-messages/) (Schließen von Tickets mithilfe von Commit-Nachrichten).

Das .NET-Team überprüft Ihren PR und teilt Ihnen mit, ob für die Genehmigung noch weitere Aktualisierungen/Änderungen erforderlich sind.

**Schritt 5:** Nehmen Sie, wie mit dem Team besprochen, alle erforderlichen Aktualisierungen in Ihrem Branch vor.

Nachdem das Feedback angewendet und die Änderung genehmigt wurde, führen die Verwalter Ihren PR mit dem Master-Branch zusammen.

In einem bestimmten Rhythmus übertragen wir alle Commits mithilfe von Push aus dem Master-Branch in den Live-Branch. Dann können Sie Ihren Beitrag live auf https://docs.microsoft.com/dotnet/ sehen.

### <a name="contributing-to-samples"></a>Mitwirken an Beispielen

Bei Code, der in unserem Repository vorhanden ist, nehmen wir folgende Unterscheidungen vor:

- Beispiele: Leser können die Beispiele herunterladen und ausführen. Alle Beispiele sollten vollständige Anwendungen oder Bibliotheken sein. Wenn mit dem Beispiel eine Bibliothek erstellt wird, sollte diese Komponententests oder eine Anwendung enthalten, mit der Leser den Code ausführen können.

- Codeausschnitte: Sie veranschaulichen ein kleineres Konzept oder eine kleinere Aufgabe. Sie können kompiliert werden, sind aber nicht als vollständige Anwendungen vorgesehen.

Der gesamte Code befindet sich im Repository [dotnet/samples](https://github.com/dotnet/samples). Wir arbeiten an einem Modell, bei dem die Ordnerstruktur für die Beispiele der Ordnerstruktur für die Dokumente entspricht. Wir richten uns nach folgenden Standards:

- Der Ordner *snippets* (Codeausschnitte) auf oberster Ebene enthält Codeausschnitte für kleine Beispiele mit Fokus.
- API-Referenzbeispiele befinden sich in einem Ordner nach folgendem Muster: *snippets/\<Sprache>/api/\<namespace>/\<API-Name>* .
- Andere Ordner auf oberster Ebene entsprechen den Ordnern auf oberster Ebene im Repository *docs*. Beispiel: Das Repository „docs“ enthält einen Ordner *machine-learning/tutorials*. Die Beispiele für die Machine Learning-Tutorials befinden sich im Ordner *samples/machine-learning/tutorials*.

Darüber hinaus sollten alle Beispiele in den Ordnern *core* und *standard* auf allen von .NET Core unterstützten Plattformen erstellt und ausgeführt werden können. Das wird durch unser CI-Build-System erzwungen. Der Ordner *Framework* auf oberster Ebene enthält Beispiele, die nur unter Windows erstellt und validiert werden.

Wir werden diese Verzeichnisse möglicherweise erweitern, wenn das Repository „docs“ neue Inhalte hinzufügt. Wir werden beispielsweise Xamarin-Verzeichnisse (z. B. `xamarin-ios` und `xamarin-android`) hinzufügen.

Jedes vollständige Beispiel, das Sie erstellen, sollte eine Datei *readme.md* enthalten. Diese Datei sollte eine kurze Beschreibung des Beispiels (ein oder zwei Absätze) enthalten. Die Datei *readme.md* soll dem Leser erläutern, was er durch das Untersuchen dieses Beispiels lernt. Die Datei *readme.md* sollte auch einen Link zu dem Live-Dokument auf der Website [.NET-Dokumentation](https://docs.microsoft.com/dotnet/welcome) enthalten.
Um zu bestimmen, wenn eine bestimmte Datei im Repository dieser Website zugeordnet ist, ersetzen Sie `/docs` im Repository-Pfad durch `https://docs.microsoft.com/dotnet`.

Ihr Thema enthält auch Links zum Beispiel. Erstellen Sie einen direkten Link zum Beispielordner auf GitHub.

Weitere Informationen finden Sie unter [Samples/Readme.md](https://github.com/dotnet/samples/blob/master/README.md).

## <a name="the-c-interactive-experience"></a>Die interaktive C#-Umgebung

Für kurze Codebeispiele in C# können Sie das Sprachtag `csharp-interactive` verwenden, um ein C#-Beispiel anzugeben, das im Browser ausgeführt wird. (Für Inline-Codebeispiele wird das Tag `csharp-interactive`, für von der Quelle eingefügte Codeausschnitte wird das Tag `code-csharp-interactive` verwendet.) Mit diesen Codebeispielen werden im Artikel ein Codefenster und ein Ausgabefenster angezeigt. Im Ausgabefenster werden alle durch die Ausführung des interaktiven Codes generierten Ausgaben angezeigt, sobald der Benutzer das Beispiel ausgeführt hat.

Die interaktive C#-Umgebung passt sich der Arbeitsweise mit den Beispielen an. Besucher können das Beispiel ausführen und die Ergebnisse anzeigen. Über eine Reihe von Faktoren wird bestimmt, ob das Beispiel oder der entsprechende Text Informationen zur Ausgabe enthalten soll.

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>Wann soll die erwartete Ausgabe ohne Ausführen des Beispiels angezeigt werden?

- In Artikeln, die für Anfänger gedacht sind, sollten die Ausgaben bereitgestellt werden, damit der Leser die Ausgabe bei seiner Arbeit mit der erwarteten Antwort vergleichen kann.
- Bei Beispielen, bei denen die Ausgabe integraler Bestandteil des Themas ist, sollte diese Ausgabe angezeigt werden. Beispielsweise sollte in Artikeln zu formatiertem Text ohne Ausführen des Beispiels das Textformat angezeigt werden.
- Wenn Beispiel und erwartete Ausgabe kurz sind, sollten Sie das Anzeigen der Ausgabe in Betracht ziehen. Das spart ein wenig Zeit.
- In Artikeln, in denen erläutert wird, wie die aktuelle oder die invariante Kultur die Ausgabe beeinflusst, sollte auch die erwartete Ausgabe erläutert werden. Der interaktive REPL (Read, Evaluate, Print Loop) wird auf einem Linux-basierten Host ausgeführt. Die Standardkultur und die invariante Kultur führen auf verschiedenen Betriebssystemen und Computern zu unterschiedlichen Ausgaben. Der Artikel sollte eine Erläuterung der Ausgabe in Windows-, Linux- und Mac-Systemen enthalten.

### <a name="when-to-exclude-expected-output-from-the-sample"></a>Wann soll die erwartete Ausgabe aus dem Beispiel ausgeschlossen werden?

- Bei Artikeln, in denen das Beispiel eine größere Ausgabe generiert, sollte diese Ausgabe in den Kommentaren nicht enthalten sein. Sie verdeckt den Code, nachdem das Beispiel ausgeführt wurde.
- Bei Artikeln, in denen das Beispiel ein Thema veranschaulicht, die Ausgabe für das Verständnis aber nicht unbedingt erforderlich ist, kann die Ausgabe ausgeschlossen werden. Beispiel: Code, der eine LINQ-Abfrage zum Erläutern der Abfragesyntax ausführt und dann jedes Element in der Ausgabeauflistung anzeigt.

## <a name="contributor-license-agreement"></a>Lizenzvereinbarung für Mitwirkende

Sie müssen das [.NET Foundation Contribution License Agreement (CLA)](https://cla.dotnetfoundation.org) unterzeichnen, bevor Ihr Pull Request zusammengeführt wird. Dies ist eine einmalige Anforderung für .NET Foundation-Projekte. Auf Wikipedia erfahren Sie mehr über [Contributor License Agreements (CLA)](https://en.wikipedia.org/wiki/Contributor_License_Agreement).

Die Vereinbarung finden Sie in der Datei [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

Sie brauchen die Vereinbarung nicht vorab zu unterzeichnen. Sie können Ihren Pull Request wie gewohnt klonen, verzweigen und übermitteln. Beim Erstellen Ihres Pull Requests wird dieser von einem CLA-Bot klassifiziert. Wenn die Änderung trivial ist (z. B. Korrigieren eines Tippfehlers), wird der Pull Request mit der Bezeichnung `cla-not-required` versehen. Andernfalls wird er als `cla-required` klassifiziert. Nachdem Sie das CLA unterzeichnet haben, werden die aktuellen und alle zukünftigen Pull Requests mit der Bezeichnung `cla-signed` versehen.
