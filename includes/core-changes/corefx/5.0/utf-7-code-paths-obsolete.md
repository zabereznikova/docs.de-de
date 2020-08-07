---
ms.openlocfilehash: 1cb6e953aa57c72ee6a2665c521bada10e0786cf
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455772"
---
### <a name="utf-7-code-paths-are-obsolete"></a>UTF-7-Codepfade sind veraltet

Die UTF-7-Codierung wird in Anwendungen kaum noch verwendet, und viele Spezifikationen [verbieten ihre Verwendung](https://security.stackexchange.com/a/68609/3573) im Austausch. Sie wird zuweilen auch in Anwendungen, die keine UTF-7-codierten Daten erwarten, [als Angriffsvektor verwendet](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7). Microsoft warnt vor der Verwendung von <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>, weil es keine Fehlererkennung bereitstellt.

Folglich sind die <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>-Eigenschaft und der <xref:System.Text.UTF7Encoding.%23ctor%2A>-Konstruktor jetzt ebenfalls veraltet. Darüber hinaus erlauben <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> und <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> nicht mehr die Angabe von `UTF-7`.

#### <a name="change-description"></a>Änderungsbeschreibung

Bisher konnten Sie mithilfe der <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>-APIs eine Instanz der UTF-7-Codierung erstellen. Zum Beispiel:

```csharp
Encoding enc1 = Encoding.GetEncoding("utf-7"); // By name.
Encoding enc2 = Encoding.GetEncoding(65000); // By code page.
```

Darüber hinaus wurde eine Instanz, die die UTF-7-Codierung repräsentiert, durch die <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType>-Methode enumeriert, wodurch alle im System registrierten <xref:System.Text.Encoding>-Instanzen enumeriert wurden.

Ab .NET 5.0 sind die <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>-Eigenschaft und die <xref:System.Text.UTF7Encoding.%23ctor%2A>-Konstruktoren veraltet und erzeugen die Warnung `SYSLIB0001` (bzw. `MSLIB0001` in Vorschauversionen). Um jedoch die Anzahl von Warnungen zu reduzieren, die Aufrufer bei Verwendung der <xref:System.Text.UTF7Encoding>-Klasse empfangen, wurde der <xref:System.Text.UTF7Encoding>-Typ selbst nicht als veraltet markiert.

```csharp
// The next line generates warning SYSLIB0001.
UTF7Encoding enc = new UTF7Encoding();
// The next line does not generate a warning.
byte[] bytes = enc.GetBytes("Hello world!");
```

Darüber hinaus behandeln die <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>-Methoden den Codierungsnamen `utf-7` und die Codepage `65000` als `unknown`. Da die Codierung als `unknown` behandelt wird, löst die Methode eine <xref:System.ArgumentException> aus.

```csharp
// Throws ArgumentException, same as calling Encoding.GetEncoding("unknown").
Encoding enc = Encoding.GetEncoding("utf-7");
```

Außerdem schließt die <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType>-Methode die UTF-7-Codierung nicht in das von ihr zurückgegebene <xref:System.Text.EncodingInfo>-Array ein. Die Codierung wird ausgeschlossen, weil sie nicht instanziiert werden kann.

```csharp
foreach (EncodingInfo encInfo in Encoding.GetEncodings())
{
    // The next line would throw if GetEncodings included UTF-7.
    Encoding enc = Encoding.GetEncoding(encInfo.Name);
}
```

#### <a name="reason-for-change"></a>Grund für die Änderung

Viele Anwendungen rufen `Encoding.GetEncoding("encoding-name")` mit einem Wert für den Codierungsnamen auf, der von einer nicht vertrauenswürdigen Quelle bereitgestellt wird. Beispielsweise könnte ein Webclient oder Webserver den `charset`-Teil des `Content-Type`-Headers verwenden und den Wert direkt an `Encoding.GetEncoding` übergeben, ohne ihn zu validieren. So könnte ein schädlicher Endpunkt `Content-Type: ...; charset=utf-7` angeben, was zu einem unerwünschten Verhalten bei der empfangenden Anwendung führen könnte.

Darüber hinaus ermöglicht die Deaktivierung von UTF-7-Codepfaden es Optimierungscompilern, wie beispielsweise denen von Blazor, diese Codepfade vollständig aus der resultierenden Anwendung zu entfernen. Im Ergebnis werden die kompilierten Anwendungen effizienter ausgeführt und belegen weniger Speicherplatz auf dem Datenträger.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

In denen meisten Fällen müssen Sie keine Maßnahmen ergreifen. Wenn Sie jedoch über Apps verfügen, in denen zuvor UTF-7-bezogene Codepfade aktiviert waren, sollten Sie sich die folgende Anleitung ansehen.

- Wenn Ihre App <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> mit unbekannten Codierungsnamen aufruft, die aus einer nicht vertrauenswürdigen Quelle stammen, gehen Sie wie folgt vor:

  Vergleichen Sie stattdessen die Codierungsnamen mit einer konfigurierbaren Zulassungsliste. Die konfigurierbare Zulassungsliste sollte mindestens den Branchenstandard „UTF-8“ enthalten. Je nach vorhandenen Clients und gesetzlichen Anforderungen müssen möglicherweise auch regionsspezifische Codierungen zulassen, wie z. B. „GB18030“.

  Wenn Sie keine Zulassungsliste implementieren, gibt <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> jede <xref:System.Text.Encoding> zurück, die im System integriert ist oder über einen benutzerdefinierten <xref:System.Text.EncodingProvider> registriert ist. Überprüfen Sie die Anforderungen Ihres Diensts, um sich zu vergewissern, dass dies das gewünschte Verhalten ist. UTF-7 ist weiterhin standardmäßig deaktiviert, es sei denn, Ihre Anwendung aktiviert den Kompatibilitätsschalter wieder, der weiter unten in diesem Artikel beschrieben wird.

- Wenn Sie <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> oder <xref:System.Text.UTF7Encoding> in Ihrem eigenen Protokoll oder Dateiformat verwenden, gehen Sie folgendermaßen vor:

  Wechseln Sie zu <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> oder <xref:System.Text.UTF8Encoding>. UTF-8 ist ein Branchenstandard und wird über Sprachen, Betriebssysteme und Runtimes hinweg flächendeckend unterstützt. Die Verwendung von UTF-8 vereinfacht die zukünftige Wartung Ihres Codes und sorgt für mehr Interoperabilität mit dem Rest des Ökosystems.

- Wenn Sie eine <xref:System.Text.Encoding>-Instanz mit <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> vergleichen, gehen Sie folgendermaßen vor:

  Erwägen Sie stattdessen eine Überprüfung anhand der bekannten UTF-7-Codepage, die `65000` lautet. Durch Vergleichen mit der Codepage vermeiden Sie die Warnung und können außerdem einige Sonderfälle behandeln, wenn beispielsweise jemand `new UTF7Encoding()` aufgerufen oder Unterklassen des Typs erstellt hat.

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

- Wenn Sie <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> oder <xref:System.Text.UTF7Encoding>verwenden müssen, gilt Folgendes:

  Sie können die `SYSLIB0001`-Warnung im Code oder in der *CSPROJ*-Datei Ihres Projekts unterdrücken.

  ```csharp
  #pragma warning disable SYSLIB0001 // Disable the warning.
  Encoding enc = Encoding.UTF7;
  #pragma warning restore SYSLIB0001 // Re-enable the warning.
  ```

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > Das Unterdrücken von `SYSLIB0001` deaktiviert nur die Warnungen, dass <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> und <xref:System.Text.UTF7Encoding> veraltet sind. Andere Warnungen werden nicht deaktiviert, und das Verhalten von APIs wie <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> wird nicht geändert.

- Wenn Sie `Encoding.GetEncoding("utf-7", ...)` unterstützen müssen, gehen Sie wie folgt vor:

  Sie können die Unterstützung über einen Kompatibilitätsschalter wieder aktivieren. Dieser Kompatibilitätsschalter kann in der *CSPROJ*-Datei der Anwendung oder in einer [Runtimekonfigurationsdatei](../../../../docs/core/run-time-config/index.md) angegeben werden, wie in den folgenden Beispielen gezeigt.

  In der *CSPROJ*-Datei der Anwendung:

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- Re-enable support for UTF-7 -->
     <EnableUnsafeUTF7Encoding>true</EnableUnsafeUTF7Encoding>
    </PropertyGroup>
  </Project>
  ```

  In der *runtimeconfig.template.json*-Datei der Anwendung:

  ```json
  {
    "configProperties": {
      "System.Text.Encoding.EnableUnsafeUTF7Encoding": true
    }
  }
  ```

  > [!TIP]
  > Wenn Sie die Unterstützung für UTF-7 wieder aktivieren, sollten Sie eine Sicherheitsüberprüfung des Codes durchführen, der <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> aufruft.

#### <a name="category"></a>Kategorie

- Core .NET-Bibliotheken
- Sicherheit

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.Encoding.UTF7?displayProperty=fullName>
- <xref:System.Text.UTF7Encoding.%23ctor>
- <xref:System.Text.UTF7Encoding.%23ctor(System.Boolean)>
- <xref:System.Text.Encoding.GetEncoding(System.Int32)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncodings?displayProperty=fullName>

<!--

#### Affected APIs

- `System.Text.Encoding.UTF7`
- `System.Text.UTF7Encoding.#ctor`
- `System.Text.UTF7Encoding.#ctor(System.Boolean)`
- `System.Text.Encoding.GetEncoding(System.Int32)`
- `System.Text.Encoding.GetEncoding(System.String)`
- `System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncodings`

-->
