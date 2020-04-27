---
title: Versionierung in C# – Leitfaden für C#
description: Informationen zur Versionierung in C# und .NET
ms.date: 01/08/2017
ms.technology: csharp-advanced-concepts
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.openlocfilehash: dc192337e4eaa5f9f1d6509ea8c15deeac34a48c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645453"
---
# <a name="versioning-in-c"></a>Versionierung in C\#

In diesem Tutorial erfahren Sie, welche Rolle die Versionierung in .NET spielt. Außerdem erfahren Sie, welche Faktoren Sie berücksichtigen müssen, wenn Sie Ihre Bibliothek versionieren oder ein Upgrade auf eine neue Version einer Bibliothek durchführen.

## <a name="authoring-libraries"></a>Erstellen von Bibliotheken

Als Entwickler, der bereits .NET-Bibliotheken für die öffentliche Verwendung erstellt hat, waren Sie bestimmt schon in Situationen, in denen Sie neue Updates implementieren mussten. Die richtige Vorgehensweise ist hier sehr wichtig, da Sie sicherstellen müssen, dass es einen nahtlosen Übergang von vorhandenem Code auf die neue Version Ihrer Bibliothek gibt. Folgendes Punkte spielen eine Rolle, wenn Sie eine neue Version erstellen:

### <a name="semantic-versioning"></a>Semantische Versionskontrolle

[Semantic versioning](https://semver.org/) (Semantische Versionierung, kurz SemVer) ist eine Namenskonvention, die auf Versionen Ihrer Bibliothek angewendet wird, um bestimmte Meilensteinereignisse zu kennzeichnen.
Im Idealfall sollten es die Versionsinformationen Ihrer Bibliothek Entwicklern erleichtern, festzustellen, ob ihre Projekte, die ältere Versionen dieser Bibliothek verwenden, kompatibel sind.

Die einfachste Herangehensweise an SemVer ist das Format `MAJOR.MINOR.PATCH` mit drei Komponenten, bei dem:

- `MAJOR` inkrementiert wird, wenn Sie nicht kompatible API-Änderungen durchführen
- `MINOR` inkrementiert wird, wenn Sie abwärtskompatible Funktionalität hinzufügen
- `PATCH` inkrementiert wird, wenn Sie abwärtskompatible Fehlerkorrekturen durchführen

Es besteht auch die Möglichkeit, andere Szenarios wie Vorabversionen usw. anzugeben, wenn Sie die Versionsinformationen auf Ihre .NET-Bibliothek anwenden.

### <a name="backwards-compatibility"></a>Abwärtskompatibilität

Die Abwärtskompatibilität mit früheren Versionen ist wahrscheinlich eine Ihrer Hauptsorgen, wenn Sie neue Versionen Ihrer Bibliothek veröffentlichen.
Bei einer neuen Version Ihrer Bibliothek besteht Quellenkompatibilität mit einer früheren Version, wenn Code, der von früheren Versionen abhängt, durch erneutes Kompilieren mit der neuen Version funktionieren kann.
Bei einer neuen Version Ihrer Bibliothek besteht binäre Kompatibilität, wenn eine Anwendung, die von der alten Versionen abhängt, ohne erneutes Kompilieren mit der neuen Version arbeiten kann.

Folgende Punkte sollten Sie beachten, wenn Sie versuchen die Abwärtskompatibilität mit älteren Versionen ihrer Bibliothek aufrechtzuerhalten:

- Virtuelle Methoden: Wenn Sie eine virtuelle Methode in Ihrer neuen Version in eine nicht-virtuelle Methode umwandeln, bedeutet das, dass die Projekte, die diese Methode außer Kraft setzen, aktualisiert werden müssen. Es handelt sich um eine schwere grundlegende Änderung, von der stark abgeraten wird.
- Methodensignaturen: Wenn Sie beim Aktualisieren des Verhaltens einer Methode ebenfalls deren Signatur ändern müssen, sollten Sie stattdessen eine Überladung erstellen, damit der Code, der diese Methode aufruft, weiterhin funktioniert.
Sie können die alte Methodensignatur immer so ändern, dass sie die neue Methodensignatur aufruft. Dadurch bleibt die Implementierung konsistent.
- [Obsolete-Attribut](language-reference/attributes/general.md#obsolete-attribute): Sie können dieses Attribut in Ihrem Code verwenden, um Klassen oder Klassenmember anzugeben, die veraltet sind und in zukünftigen Versionen vermutlich gelöscht werden. Dadurch sind Entwickler, die Ihre Bibliothek verwenden, besser auf grundlegende Änderungen vorbereitet.
- Optionale Methodenargumente: Wenn sie vorher optionale in obligatorische Methodenargumente umwandeln oder ihren Standardwert ändern, muss der gesamte Code, der diese Argumente nicht bereitstellt, aktualisiert werden.

> [!NOTE]
> Die Umwandlung von obligatorischen Argumenten in optionale sollte nur geringe Auswirkungen haben, besonders, wenn dadurch das Verhalten der Methode nicht geändert wird.

Je leichter Sie es Ihren Benutzern machen, auf die neue Version Ihrer Bibliothek zu aktualisieren, desto früher werden sie dieses Upgrade durchführen.

### <a name="application-configuration-file"></a>Anwendungskonfigurationsdatei

Als .NET-Entwickler haben Sie sehr wahrscheinlich schon einmal mit [der `app.config`-Datei](../framework/configure-apps/file-schema/index.md) gearbeitet, die in den meisten Projekttypen enthalten ist.
Diese einfache Konfigurationsdatei kann beim Verbessern der Einführung neuer Updates einen großen Unterschied machen. In der Regel sollten Sie Ihre Bibliotheken so anlegen, dass die Informationen, die sich wahrscheinlich häufiger ändern, in der Datei `app.config` gespeichert werden. Auf diese Weise muss die Konfigurationsdatei früherer Versionen nur durch die neue Datei ersetzt werden, wenn solche Informationen aktualisiert werden. Eine erneute Kompilierung der Bibliothek ist nicht mehr erforderlich.

## <a name="consuming-libraries"></a>Verarbeiten von Bibliotheken

Als Entwickler, der .NET-Bibliotheken verarbeitet, die von anderen Entwicklern erstellt wurden, sind Sie sich sicher der Tatsache bewusst, dass eine neue Version einer Bibliothek möglicherweise nicht voll kompatibel mit Ihrem Projekt ist, und Sie Ihren Code oft aktualisieren müssen, um auf diese Änderungen zu reagieren.

Glücklicherweise gibt es in C#-und dem .NET-Ökosystem Features und Techniken, mit denen Sie Apps leicht aktualisieren können, damit sie mit neuen Versionen von Bibliotheken funktionieren, mit denen möglicherweise Breaking Changes eingeführt werden.

### <a name="assembly-binding-redirection"></a>Assemblybindungsumleitung

Sie können die Datei *app.config* zum Aktualisieren der Version einer von Ihrer App verwendeten Bibliothek verwenden. Durch Hinzufügen einer sogenannten [*Bindungsumleitung*](../framework/configure-apps/redirect-assembly-versions.md) können Sie die neue Version der Bibliothek verwenden, ohne dass Sie Ihre App erneut kompilieren müssen. Im folgenden Beispiel wird gezeigt, wie Sie die *app.config*-Datei Ihrer App aktualisieren, um die Patchversion `1.0.1` von `ReferencedLibrary` zu verwenden, statt der Version `1.0.0`, mit der sie ursprünglich kompiliert wurde.

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> Dieser Ansatz funktioniert nur, wenn die neue Version von `ReferencedLibrary` binär kompatibel mit Ihrer Anwendung ist.
> Im Abschnitt [Abwärtskompatibilität](#backwards-compatibility) finden Sie Änderungen, die Sie beachten müssen, wenn Sie die Kompatibilität bestimmen.

### <a name="new"></a>neu

Sie können den `new`-Modifizierer verwenden, um geerbte Member einer Basisklasse auszublenden. Dies ist eine Möglichkeit, wie abgeleitete Klassen auf Updates in Basisklassen reagieren können.

Betrachten Sie das folgende Beispiel:

[!code-csharp[Sample usage of the 'new' modifier](~/samples/snippets/csharp/versioning/new/Program.cs#sample)]

**Ausgabe**

```console
A base method
A derived method
```

Im obigen Beispiel können Sie sehen, wie `DerivedClass` die Methode `MyMethod` ausblendet, die sich in `BaseClass` befindet.
Das bedeutet, dass Sie einfach den `new`-Modifizierer auf Ihre abgeleiteten Klassenmember anwenden können, um die Member der Basisklasse auszublenden, wenn von einer Basisklasse in der neuen Version einer Bibliothek Member hinzugefügt werden, die sich bereits in Ihrer abgeleiteten Klasse befinden.

Wenn kein `new`-Modifizierer angegeben ist, blendet eine abgeleitete Klasse standardmäßig in Konflikt stehende Member in der Basisklasse aus. Obwohl eine Compilerwarnung generiert wird, kompiliert der Code weiter. Das bedeutet, dass die neue Version Ihrer Bibliothek durch das Hinzufügen neuer Member zu einer vorhanden Klasse sowohl quellen- als auch binär kompatibel mit dem Code wird, der von ihr abhängt.

### <a name="override"></a>override

Der `override`-Modifizierer bedeutet, dass eine abgeleitete Implementierung die Implementierung eines Basisklassenmembers erweitert, anstatt sie auszublenden. Der `virtual`-Modifizierer muss auf den Basisklassenmember angewendet sein.

[!code-csharp[Sample usage of the 'override' modifier](../../samples/snippets/csharp/versioning/override/Program.cs#sample)]

**Ausgabe**

```console
Base Method One: Method One
Derived Method One: Derived Method One
```

Der `override`-Modifizierer wird beim Kompilieren ausgewertet, und der Compiler löst einen Fehler aus, wenn kein virtueller Member gefunden wird, der außer Kraft gesetzt werden kann.

Ihre Kenntnis der besprochenen Techniken und Ihr Wissen, in welchen Situationen diese angewendet werden, wird wesentlich dazu beitragen, den Übergang zwischen den Versionen einer Bibliothek zu erleichtern.
