---
title: Breaking Changes und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Umgang mit Breaking Changes beim Erstellen von .NET-Bibliotheken.
ms.date: 10/02/2018
ms.openlocfilehash: 2cbd9e0a818b52aede6c9b1f60fdf52dcbd7b96f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398508"
---
# <a name="breaking-changes"></a>Breaking Changes

Es ist wichtig für eine .NET-Bibliothek, ein Gleichgewicht zwischen Stabilität für bestehende Benutzer und Innovation für die Zukunft zu finden. Ersteller von Bibliotheken verändern Code gelegentlich, bis er ihren Ansprüchen entspricht. Allerdings haben Unterbrechungen negative Auswirkungen auf Ihre Benutzer, besonders bei Bibliotheken auf niedriger Ebene.

## <a name="project-types-and-breaking-changes"></a>Projekttypen und Breaking Changes

Wie eine Bibliothek von der .NET-Community verwendet wird, ändert die Auswirkungen von Breaking Changes auf die Endbenutzerentwickler.

- **Bibliotheken auf niedriger und mittlerer Ebene** wie Serialisierungsmodule, HTML-Parser, datenbankobjektrelationale Mapper oder Webframeworks sind am stärksten von Breaking Changes betroffen.

  Bausteinpakete werden von Endbenutzerentwicklern zum Erstellen von Anwendungen und von anderen Bibliotheken für NuGet-Abhängigkeiten verwendet. Angenommen, Sie erstellen eine Anwendung und verwenden einen Open Source-Client zum Aufrufen eines Webdiensts. Sie können kein wichtiges Update für eine Abhängigkeit korrigieren, die der Client verwendet. Der Open Source-Client muss nämlich geändert werden, und das können Sie nicht steuern. Sie müssen kompatible Bibliotheksversionen finden oder einen Fix an die Clientbibliothek übermitteln und auf eine neue Version warten. Der schlimmste Fall ist, wenn Sie zwei Bibliotheken verwenden wollen, die von gegenseitig inkompatiblen Versionen einer dritten Bibliothek abhängen.

- **Bibliotheken auf hoher Ebene** wie eine Sammlung von Steuerelementen der Benutzeroberfläche sind weniger anfällig für Breaking Changes.

  Bibliotheken auf hoher Ebene werden direkt in einer Endbenutzeranwendung referenziert. Wenn Breaking Changes auftreten, kann der Entwickler ein Update auf die neueste Version ausführen oder seine Anwendung ändern, um die Breaking Changes zu verwenden.

✔️️ Überlegen Sie, wie Ihre Bibliothek verwendet werden wird. Welche Auswirkungen haben Breaking Changes auf Anwendungen und Bibliotheken, die diese verwenden?

✔️ Minimieren Sie Breaking Changes beim Entwickeln einer .NET-Bibliothek auf niedriger Ebene.

✔️ Veröffentlichen Sie eine in großen Teilen umgeschriebene Bibliothek gegebenenfalls als neues NuGet-Paket.

## <a name="types-of-breaking-changes"></a>Arten von Breaking Changes

Breaking Changes lassen sich in unterschiedliche Kategorien unterteilen und sind nicht gleichermaßen wirkungsvoll.

### <a name="source-breaking-change"></a>Breaking Changes in der Quelle

Breaking Changes in der Quelle wirken sich nicht auf die Programmausführung aus, verursachen allerdings Kompilierungsfehler, wenn die Anwendung das nächste Mal erneut kompiliert wird. Beispielsweise kann eine neue Überladung eine Mehrdeutigkeit bei Methodenaufrufen erzeugen, die zuvor eindeutig waren, oder aber ein umbenannter Parameter unterbricht Aufrufer, die benannte Parameter verwenden.

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

Da Breaking Changes in der Quelle nur dann schädlich sind, wenn Entwickler ihre Anwendungen erneut kompilieren, handelt es sich dabei um die harmlosesten Breaking Changes. Entwickler können ihren eigenen fehlerhaften Quellcode einfach reparieren.

### <a name="behavior-breaking-change"></a>Behavior Breaking Changes

Änderungen am Verhalten sind die häufigste Art von Breaking Changes: Fast jeder Behavior Change wirkt sich negativ auf die Benutzer aus. Änderungen an Ihrer Bibliothek, z.B. Methodensignaturen, ausgelöste Ausnahmen oder Ein- bzw. Ausgabedatenformaten, können sich negativ auf Ihre Bibliotheksnutzer auswirken. Sogar eine Fehlerbehebung kann ein Breaking Change sein, wenn sich Benutzer auf das ehemals fehlerhafte Verhalten verlassen haben.

Das Hinzufügen von Funktionen und Verbessern von schlechtem Verhalten wird empfohlen. Wenn diese Vorgänge jedoch nicht richtig ausgeführt werden, können vorhandene Benutzer Schwierigkeiten mit Upgrades haben. Ein Entwickler unterstützender Ansatz beim Umgang mit Behavior Breaking Changes besteht darin, sie hinter Einstellungen zu verstecken. Mithilfe von Einstellungen können Entwickler auf die neueste Version Ihrer Bibliothek aktualisieren und dabei entscheiden, ob sie Änderungen vornehmen oder nicht. Diese Strategie ermöglicht es Entwicklern, auf dem neuesten Stand zu bleiben und zugleich ihren genutzten Code mit der Zeit anzupassen.

So umfasst ASP.NET Core MVC beispielsweise das Konzept einer [Kompatibilitätsversion](/aspnet/core/mvc/compatibility-version), die die unter `MvcOptions` aktivierten und deaktivierten Funktionen ändert.

✔️ Deaktivieren Sie neue Features gegebenenfalls standardmäßig, wenn sie vorhandene Benutzer beeinträchtigen. Geben Sie Entwicklern die Möglichkeit, diese Features mit einer Einstellung zu aktivieren.

### <a name="binary-breaking-change"></a>Binäre Breaking Changes

Ein binärer Breaking Change tritt auf, wenn Sie die öffentliche API Ihrer Bibliothek ändern, sodass Assemblys, die mit älteren Versionen Ihrer Bibliothek kompiliert wurden, die API nicht mehr aufrufen können. Wenn Sie beispielsweise die Signatur einer Methode durch Hinzufügen eines neuen Parameters ändern, werden Assemblys, die mit einer älteren Bibliotheksversion kompiliert wurden, ein <xref:System.MissingMethodException>-Ausnahme auslösen.

Eine binärer Breaking Change kann auch eine **ganze Assembly** unterbrechen. Das Umbenennen einer Assembly mit `AssemblyName` ändert die Identität der Assembly ebenso wie das Hinzufügen, Entfernen oder Ändern des starken Namensschlüssels der Assembly. Eine Änderung der Identität einer Assembly unterbricht alle kompilierten Codes, die diese verwenden.

❌ Ändern Sie keine Assemblynamen.

❌ Den Schlüssel für die eindeutige Benennung weder hinzufügen, noch ändern oder entfernen

✔️ Verwenden Sie abstrakte Basisklassen anstelle von Schnittstellen.

> Wenn Sie einer Schnittstelle etwas hinzufügen, tritt ein Fehler für vorhandene Typen auf, die diese implementieren. Mit einer abstrakten Basisklasse können Sie eine standardmäßige virtuelle Implementierung hinzufügen.

✔️ Platzieren Sie auf Typen und Membern, die Sie entfernen möchten, gegebenenfalls das <xref:System.ObsoleteAttribute>. Das Attribut muss Anweisungen zum Aktualisieren des Codes enthalten, damit die veraltete API nicht mehr verwendet wird.

> Code, der Typen und Methoden mit <xref:System.ObsoleteAttribute> aufruft, generiert eine Buildwarnung mit der Meldung, die an das Attribut übergeben wird. Warnungen geben Personen, die die veraltete API verwenden, Zeit zum Migrieren, sodass die meisten Benutzer, wenn die veraltete API entfernt wird, diese nicht mehr verwenden.

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

✔️ Behalten Sie Typen und Methoden mit <xref:System.ObsoleteAttribute> auf unbestimmte Zeit in Bibliotheken auf niedriger und mittlerer Ebene bei.

> Das Entfernen von APIs ist eine binärer Breaking Change. Erwägen Sie, veraltete Typen und Methoden beizubehalten, falls ihre Verwaltung keinen kostspieligen und großen technischen Aufwand für die Bibliothek bedeutet. Wenn Sie Typen und Methoden nicht entfernen, können Sie so die obigen Worst-Case-Szenarios vermeiden.

## <a name="see-also"></a>Weitere Informationen

- [Versions- und Updateüberlegungen für C#-Entwickler](../../csharp/whats-new/version-update-considerations.md)
- [Umfassendes Handbuch für API-Breaking Changes in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
- [Regeln von Breaking Changes in .NET](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
>[Zurück](versioning.md)
