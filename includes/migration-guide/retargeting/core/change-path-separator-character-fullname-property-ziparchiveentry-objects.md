---
ms.openlocfilehash: 148312743dd274728b178951548889dc3a680528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614466"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>Änderung bei Pfadtrennzeichen in der FullName-Eigenschaft von ZipArchiveEntry-Objekten

#### <a name="details"></a>Details

Bei Apps für .NET Framework 4.6.1 und höhere Versionen hat sich das Pfadtrennzeichen in der <xref:System.IO.Compression.ZipArchiveEntry.FullName>-Eigenschaft von <xref:System.IO.Compression.ZipArchiveEntry>-Objekten, die durch Überladungen der <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A>-Methode erstellt wurden, von einem umgekehrten Schrägstrich (\") in einen normalen Schrägstrich (/) geändert. Die Änderung bringt die .NET-Implementierung in Einklang mit Abschnitt 4.4.17.1 der [ZIP-Dateiformatspezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) und ermöglicht es, dass ZIP-Archive auf Nicht-Windows-Systemen entpackt werden.<br />Beim Dekomprimieren einer ZIP-Datei, die für eine frühere Version der .NET Framework-Zielplattform unter einem anderen als dem Windows-Betriebssystem – wie etwa dem Macintosh – erstellt wurde, bleibt die Verzeichnisstruktur nicht erhalten. Beispielsweise werden auf einem Macintosh mehrere Dateien erstellt, deren Dateinamen eine Verkettung aus dem Verzeichnispfad, allen vorhandenen umgekehrten Schrägstrichzeichen ("") und dem Dateinamen darstellen. Im Ergebnis wird die Verzeichnisstruktur der dekomprimierten Dateien nicht beibehalten.

#### <a name="suggestion"></a>Vorschlag

Die Auswirkungen dieser Änderungen auf ZIP-Dateien, die unter dem Windows-Betriebssystem durch die APIs im .NET Framework <xref:System.IO?displayProperty=nameWithType>-Namespace dekomprimiert werden, sollten minimal sein, da diese APIs sowohl den einfachen Schrägstrich (/) als auch den umgekehrten Schrägstrich (\") als Pfadtrennzeichen verarbeiten können.<br />Wenn diese Änderung nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie dem Abschnitt [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen. Im folgenden Beispiel sind sowohl der Abschnitt `<runtime>` als auch die Ablehnungsoption `Switch.System.IO.Compression.ZipFile.UseBackslash` dargestellt:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

Darüber hinaus kann für Apps mit früheren Versionen von .NET Framework als Zielplattform, die unter .NET Framework 4.6.1 und neueren Versionen ausgeführt werden, die Verwendung dieses Verhaltens akzeptiert werden, indem Sie dem Abschnitt [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen. Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch die Option `Switch.System.IO.Compression.ZipFile.UseBackslash` zur Verwendung dieses Verhaltens dargestellt.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
