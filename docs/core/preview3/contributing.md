# <a name="using-the-preview3-folder-and-sub-folders"></a>Verwenden des Ordners „preview3“ und der Unterordner

Dieser Ordner ist der Knoten der obersten Ebene, der mit dem Tools-Ordner übereinstimmt. Er enthält jedoch Deltas für das Release von .NET Core Tools RC4.

Das Ziel dieser separaten parallelen Ordnerstruktur ist, einen Speicherort für den Inhalt im Zusammenhang mit dem RC&4;-Release bereitzustellen, der beim Versionswechsel in der veröffentlichten Website relativ leicht mit der Hauptstruktur zusammengeführt werden kann.

Der Inhalt unter diesem Knoten sollte eine kleinere Reihe von Dokumenten sein, die die Deltas aus der LTS-Version (Long Term Support, langfristige Unterstützung) und der neuesten aktuellen Version darstellen. 

## <a name="structure"></a>Struktur

Es gibt zwei Fälle, in denen neue Inhalte für diese Version hinzugefügt werden:

* Änderungen an vorhandenen Dokumenten
    - Kopieren Sie den vorhandenen Inhalt in einen parallelen Ordner in dieser Struktur. Nehmen Sie Ihre Änderungen vor, und fügen Sie die geänderte Datei zum Inhaltsverzeichnis für das RC4-Release hinzu.
* Neue Dokumente
    - Legen Sie das neue Dokument am richtigen Speicherort ab, und fügen Sie es dem Inhaltsverzeichnis unter dem Knoten für das RC4-Release hinzu. 

Bei allen Dateien der aktuellen Version sollte am Anfang des Themas Folgendes hinzugefügt werden:

[!include[current release track](../includes/warning.md)]

Wir haben einen einzubindenden Ausschnitt mit der folgenden Syntax erstellt:

```markdown
[!include[current release track](../../includes/warning.md)]
```

### <a name="link-instructions"></a>Anweisungen für Links

Geben Sie für die Navigation in beiden Fällen Links der aktuellen Version zur LTS-Seite (oder der übergeordneten „index.md“) an.
Sie könnten auch Links von der LTS-Seite (oder der übergeordneten „index.md“) zur Inhaltsseite der neuen aktuellen Version bereitstellen.

## <a name="future-considerations"></a>Überlegungen für die Zukunft

Unser Ziel ist es, verschiedene Versionen als Zweige im [Dokumentrepository](https://github.com/dotnet/docs) darzustellen. Bis das Veröffentlichungsszenario unterstützt wird, verwenden wir unterschiedliche Ordner der obersten Ebene für jede aktuelle Version. 

Zu gegebener Zeit können wir jede aktuelle Version im Hauptordner [docs](../docs) zusammenführen, die Knoten des Inhaltsverzeichnisses zusammenführen und eine separate Reihe von Dokumenten veröffentlichen. Möglicherweise müssen Änderungen an der LTS-Version einer Datei und der aktuellen Version einer Datei zusammengeführt werden. Wir sollten diese Änderungen jedoch relativ leicht finden können.


<!--HONumber=Feb17_HO2-->


