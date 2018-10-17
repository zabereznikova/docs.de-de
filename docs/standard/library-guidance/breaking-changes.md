---
title: Wichtige Änderungen und Bibliotheken für .NET
description: Empfehlungen für bewährte Methoden navigieren, wichtige Änderungen, wenn Sie Bibliotheken für .NET zu erstellen.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370063"
---
# <a name="breaking-changes"></a>Wichtige Änderungen

Es ist wichtig für die eine .NET-Bibliothek finden Sie ein Gleichgewicht zwischen Stabilität für vorhandene Benutzer und Innovationen für die Zukunft. Autoren von Klassenbibliotheken erfahren Sie, für die Umgestaltung und neuer Ansatz für Code, bis er sich hervorragend eignet, aber Ihre vorhandenen Benutzer wichtige negative Auswirkungen, insbesondere für Low-Level-Bibliotheken hat.

## <a name="project-types-and-breaking-changes"></a>Projekttypen und wichtige Änderungen

Die Auswirkungen der Änderungen für endbenutzerentwickler, die durch den ändert sich wie eine Bibliothek von der .NET-Community zuzog verwendet wird.

* **Niedrig und mittleren Stufe Bibliotheken** wie ein Serialisierungsprogramm, HTML-Parser, objektrelationale Zuordnung Datenbank oder Web-Framework sind die betroffenen wichtige Änderungen.

  Baustein-Pakete werden als NuGet-Abhängigkeiten von Endbenutzer-Entwicklern zum Erstellen von Anwendungen und von anderen Bibliotheken verwendet werden. Z. B. Sie eine Anwendung entwickeln und einen Open-Source-Client auf einen Webdienst aufzurufen. Eine wichtige-Update für eine Abhängigkeit, die der Client verwendet, nicht, die Sie beheben können. Es ist der Open-Source-Client, der geändert werden muss, und Sie haben keine Kontrolle darüber. Sie müssen kompatible Versionen der Bibliotheken finden oder senden eine Lösung für die Clientbibliothek, und warten, bis eine neue Version. Den schlimmsten Fall ist, sollten Sie zwei Bibliotheken verwenden, die auf inkompatible Versionen von einer dritten-Bibliothek abhängig sind.

* **Allgemeine Bibliotheken** wie eine Sammlung von UI-Steuerelemente sind weniger anfällig für wichtige Änderungen.

  Allgemeine Bibliotheken werden direkt in einer endbenutzeranwendung auf die verwiesen wird. Wenn Änderungen auftreten, wird der Entwickler kann auch auf die neueste Version zu aktualisieren, oder Ändern ihrer Anwendung zur Zusammenarbeit mit der grundlegenden Änderungen.

**Führen Sie ✔️** überlegen, wie die Bibliothek verwendet werden soll. Welche Auswirkungen haben wichtige Änderungen auf Anwendungen und Bibliotheken, die sie verwenden?

**Führen Sie ✔️** Änderungen minimiert werden, wenn eine .NET-Bibliothek auf niedriger Ebene zu entwickeln.

**✔️ GGF.** veröffentlichen eine größere schreiben, einer Bibliothek als neue NuGet-Paket.

## <a name="types-of-breaking-changes"></a>Arten von Änderungen

Wichtige Änderungen in verschiedene Kategorien fallen, und es sind nicht gleichmäßig eindrucksvolle.

### <a name="source-breaking-change"></a>Wichtige Änderung an der Datenquelle

Eine Quelle, die wichtige Änderung führt betrifft keine Ausführung des Programms aber zu Kompilierungsfehler das nächste Mal, die, das die Anwendung erneut kompiliert wird. Z. B. eine neue Überladung kann eine Mehrdeutigkeit in Methodenaufrufe, die eindeutig früher erstellen, oder ein umbenannter Parameter unterbricht Aufrufer, mit denen benannte Parameter.

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

Da es sich bei eine Quelle, die wichtige Änderung nur schädlich ist, wenn Entwickler ihre Anwendungen neu kompilieren, ist es am wenigsten störenden wichtige Änderung. Entwickler können ihre eigenen unterbrochen Quellcode einfach beheben.

### <a name="behavior-breaking-change"></a>Wichtige verhaltensänderung

Verändertes Programmverhalten sind der am häufigsten verwendeten wichtige Änderung: nahezu jede Änderung im Verhalten kann ein Benutzer unterbrochen. Änderungen an Ihrer Bibliothek, z. B. Methodensignaturen Ausnahmen ausgelöst oder Eingabe oder Ausgabe Datenformate, könnten alle beeinträchtigt Ihre Consumer. Als fehlerhafte Änderung können sogar eine Programmfehlerbehebung qualifizieren, wenn Benutzer auf das zuvor fehlerhaften Verhalten beruhte.

Hinzufügen von Funktionen und schlechte Verhaltensweisen verbessern, ist eine gute Sache, aber ohne Sorgfalt können erleichtern es sehr schwierig für vorhandene Benutzer aktualisieren. Ein Ansatz zum Schutz von Entwicklern, die Behandlung von Verhalten, die wichtige Änderungen werden hinter Einstellungen ausblenden. Einstellungen können Entwickler auf die neueste Version Ihrer Bibliothek, während gleichzeitig auswählen, aktivieren oder deaktivieren die Änderungen zu aktualisieren. Diese Strategie ermöglicht Entwicklern, die auf dem neuesten Stand zu bleiben, während ihre verwendeten Code im Laufe der Zeit anpassen lassen.

Beispielsweise ASP.NET Core MVC hat das Konzept einer [Kompatibilitätsversion](/aspnet/core/mvc/compatibility-version) , ändert es sich um die Funktionen aktiviert und deaktiviert auf `MvcOptions`.

**✔️ GGF.** neue Features in der Standardeinstellung deaktiviert verlassen, wenn sie die Auswirkungen auf vorhandene Benutzer, und Entwicklern, die ermöglichen sich auf die Funktion mit einer Einstellung entscheiden.

### <a name="binary-breaking-change"></a>Binäre unterbrechende Änderung

Eine wichtige Änderung Binärdatei tritt auf, wenn Sie die öffentliche API Ihrer Bibliothek ändern, damit Assemblys kompiliert ältere Versionen Ihrer Bibliothek können nicht mehr zum Aufrufen der API. Beispielsweise ändern die Signatur einer Methode, durch Hinzufügen eines neuen Parameters führt dazu, dass Assemblys, die für die ältere Version der Bibliothek kompiliert, um auszulösen, eine <xref:System.MissingMethodException>.

Eine wichtige Änderung Binärdatei kann auch unterbrochen. eine **gesamte Assembly**. Umbenennen einer Assembly mit `AssemblyName` ändert sich der Identität der Assembly, wie hinzufügen, entfernen oder ändern den Schlüssel der Assembly starke Benennung. Eine Änderung der Identität einer Assembly werden alle kompilierten Code unterbrochen, der verwendet wird.

**❌ NICHT** Namen einer Assembly zu ändern.

**❌ NICHT** hinzufügen, entfernen oder ändern Sie den Schlüssel für starke benennungen.

**✔️ GGF.** anstelle Schnittstellen von abstrakten Basisklassen.

> Nichts hinzufügen, um eine Schnittstelle bewirkt vorhandene Typen, die Fehler zu implementieren. Eine abstrakte Basisklasse, können Sie eine Standardimplementierung für den virtuellen hinzufügen.

**✔️ GGF.** Platzieren der <xref:System.ObsoleteAttribute> für Typen und Member, die Sie entfernen möchten. Das Attribut müssen Anweisungen zum Aktualisieren von Code aus, um die veraltete API nicht mehr verwenden.

> Code, der Aufrufe von Typen und Methoden mit dem <xref:System.ObsoleteAttribute> wird eine Buildwarnung generiert, mit der Meldung, die für das Attribut angegebenen. Warnungen bieten Personen, die beim veraltet-API-Oberfläche verwenden, migrieren, damit beim Entfernen der veralteten API die meisten nicht mehr sind Verwendung.

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

## <a name="see-also"></a>Siehe auch

* [Überlegungen zur Version und Updates für C#-Entwickler](../../csharp/whats-new/version-update-considerations.md)
* [Endgültiger Leitfaden zur API-Änderungen in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [CoreFX wichtige Ändern der Regeln](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[Vorherige](./versioning.md)
