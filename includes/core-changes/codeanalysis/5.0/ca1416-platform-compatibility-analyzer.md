---
ms.openlocfilehash: 4a7616d2ffaabab5279342ebc1082c93a174a52d
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406171"
---
### <a name="ca1416-platform-compatibility"></a>CA1416: Plattformkompatibilität

Die .NET-Codeanalyseregel [CA1416](/visualstudio/code-quality/ca1416) ist ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für Aufrufe an plattformspezifische APIs von Aufrufsites, bei denen das Betriebssystem nicht überprüft wird.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md). Einige dieser Regeln, darunter [CA1416](/visualstudio/code-quality/ca1416), sind standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln. Die Regel CA1416 informiert Sie darüber, wenn Sie plattformspezifische APIs über Orte verwenden, an denen der Plattformkontext nicht überprüft wird.

Regel [CA1416](/visualstudio/code-quality/ca1416), das Analysetool für die Plattformkompatibilität, arbeitet mit einigen anderen Features zusammen, die neu in .NET 5.0 sind. In NET 5.0 werden <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> und <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> eingeführt, mit denen Sie die Plattformen angeben können, auf denen eine API *unterstützt wird* oder *nicht*. Wenn diese Attribute nicht vorhanden sind, wird davon ausgegangen, dass eine API auf allen Plattformen unterstützt wird. Diese Attribute wurden auf plattformspezifische APIs in den wichtigsten .NET-Bibliotheken angewendet.

In Projekten für Plattformen, für die die verwendeten APIs nicht verfügbar sind, kennzeichnet die Regel [CA1416](/visualstudio/code-quality/ca1416) alle plattformspezifischen API-Aufrufe, bei denen der Plattformkontext nicht überprüft wird. Die meisten APIs, die nun mit den Attributen <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> und <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> versehen sind, lösen <xref:System.PlatformNotSupportedException>-Ausnahmen aus, wenn sie unter einem nicht unterstützten Betriebssystem aufgerufen werden. Da diese APIs nun als plattformspezifisch gekennzeichnet sind, hilft Ihnen die Regel [CA1416](/visualstudio/code-quality/ca1416) dabei, <xref:System.PlatformNotSupportedException>-Ausnahmen zur Laufzeit zu verhindern, indem Überprüfungen des Betriebssystems zu Ihren Aufrufsites hinzugefügt werden.

#### <a name="examples"></a>Beispiele

- Die Methode <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> wird nur unter Windows unterstützt, und sie ist mit `[SupportedOSPlatform("windows")]` versehen. Der folgende Code erzeugt eine CA1416-Warnung zur Buildzeit, wenn im Projekt `net5.0` [als Ziel angegeben ist](../../../../docs/standard/frameworks.md) (aber nicht `net5.0-windows`). Mögliche Maßnahmen, um diese Warnung zu vermeiden, finden Sie unter [Empfohlene Maßnahme](#recommended-action).

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- Die Methode <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> wird im Browser nicht unterstützt, und sie ist mit `[UnsupportedOSPlatform("browser")]` versehen. Der folgende Code erzeugt eine CA1416-Warnung zur Buildzeit, wenn das Projekt die Browserplattform unterstützt.

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

  > [!TIP]
  >
  > - In Blazor WebAssembly-Projekten und Projekten der Razor-Klassenbibliothek ist die Browserunterstützung automatisch enthalten.
  > - Wenn Sie den Browser manuell als unterstützte Plattform Ihrem Projekt hinzufügen möchten, fügen Sie den folgenden Eintrag zu Ihrer Projektdatei hinzu:
  >
  >  ```xml
  >  <ItemGroup>
  >    <SupportedPlatform Include="browser" />
  >  </ItemGroup>
  >  ```

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC1

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Stellen Sie sicher, dass plattformspezifische APIs nur aufgerufen werden, wenn der Code auf der entsprechenden Plattform ausgeführt wird. Sie können vor dem Aufrufen einer plattformspezifischen API mithilfe einer der `Is<Platform>`-Methoden in der Klasse <xref:System.OperatingSystem?displayProperty=nameWithType>, z. B. <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, das aktuelle Betriebssystem überprüfen.

Sie können eine der `Is<Platform>`-Methoden in der Bedingung einer `if`-Anweisung verwenden:

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

Wenn Sie den Aufwand einer zusätzlichen `if`-Anweisung zur Laufzeit vermeiden möchten, können Sie alternativ <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> aufrufen:

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

Wenn Sie eine Bibliothek erstellen, können Sie Ihre API als plattformspezifisch markieren. In diesem Fall fällt der Aufwand für die Überprüfung von Anforderungen für Ihre Aufrufer weg. Sie können bestimmte Methoden oder Typen oder eine gesamte Assembly markieren.

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

Wenn Sie nicht alle Ihre Aufrufsites ändern möchten, können Sie die Warnung durch eine der folgenden Vorgehensweisen unterdrücken:

- Wenn Sie die Regel CA1416 unterdrücken möchten, können Sie hierfür `#pragma` oder das Compilerflag [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) verwenden oder als [Schweregrad für die Regel](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) in einer .editorconfig-Datei `none` festlegen.

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Category

- Codeanalyse
- Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

Für die Windows-Plattform:

- Alle unter <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md> aufgeführten APIs
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

Für die Blazor WebAssembly-Plattform:

- Alle unter <https://github.com/dotnet/runtime/issues/41087> aufgeführten APIs

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a>Weitere Informationen

- [CA1416: Plattformkompatibilität überprüfen](/visualstudio/code-quality/ca1416)
- [.NET API-Analysetool](../../../../docs/standard/analyzers/api-analyzer.md)
