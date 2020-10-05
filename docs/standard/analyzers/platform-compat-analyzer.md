---
title: Analysetool für die Plattformkompatibilität
description: Ein Roslyn-Analysetool, das helfen kann, in plattformübergreifenden Apps und Bibliotheken Probleme mit der Plattformkompatibilität zu erkennen
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 4e842e5bbe90dd5006d9b27d0365f908b6441997
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406586"
---
# <a name="platform-compatibility-analyzer"></a>Analysetool für die Plattformkompatibilität

Sie haben wahrscheinlich bereits von .NET als einer einzigen, einheitlichen Plattform für die Entwicklung beliebiger Anwendungstypen gehört. Das .NET 5.0 SDK enthält ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin und ML.NET, und Unterstützung für weitere Plattformen wird im Laufe der Zeit hinzugefügt. Es ist das Ziel von .NET 5.0, dass Sie sich keine Gedanken um die verschiedenen .NET-Varianten machen müssen, ohne dass das zugrunde liegende Betriebssystem zu diesem Zweck vollständig abstrahiert wird. Sie sind weiterhin in der Lage, plattformspezifische APIs (z. B. P/Invokes, WinRT oder die Xamarin-Bindungen für iOS und Android) aufzurufen.

Durch die Verwendung plattformspezifischer APIs für eine Komponente funktioniert der Code jedoch nicht mehr auf allen Plattformen. Es fehlte eine Methode, die dies zur Entwurfszeit erkennt, damit Entwickler eine Diagnose erhalten, wenn sie versehentlich plattformspezifische APIs verwenden. Aus diesem Grund führt .NET 5.0 das [Analysetool für die Plattformkompatibilität](/visualstudio/code-quality/ca1416) sowie ergänzende APIs ein, damit Entwickler ggf. plattformspezifische APIs erkennen und verwenden können, wenn es sinnvoll ist.
Zu den neuen APIs zählen:

- <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> zum Kommentieren von APIs als plattformspezifisch und <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, um APIs als für ein bestimmtes Betriebssystem nicht unterstützt zu annotieren. Diese Attribute können optional die Versionsnummer enthalten und wurden bereits auf einige plattformspezifische APIs in den .NET-Kernbibliotheken angewendet.
- Die statischen Methoden `Is<Platform>()` und `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` in der Klasse <xref:System.OperatingSystem?displayProperty=nameWithType> zum sicheren Aufrufen von plattformspezifischen APIs. Mit <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> kann beispielsweise ein Aufruf einer Windows-spezifischen API und mit <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() ein versionierter Windows-spezifischer API-Aufruf geschützt werden. In diesen [Beispielen](#guard-platform-specific-apis-with-guard-methods) wird veranschaulicht, wie mithilfe dieser Methoden plattformspezifische API-Verweise geschützt werden können.

> [!TIP]
> Das Analysetool für die Plattformkompatibilität aktualisiert und ersetzt das Feature für die [Ermittlung plattformübergreifender Probleme](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) des [.NET-API-Analysetools](../../standard/analyzers/api-analyzer.md).

## <a name="prerequisites"></a>Voraussetzungen

Bei dem Analysetool für die Plattformkompatibilität handelt es sich um eines der Codequalitätsanalysetools von Roslyn. Ab .NET 5.0 sind diese Analysetools im [.NET SDK](../../fundamentals/productivity/code-analysis.md) enthalten. Das Analysetool für die Plattformkompatibilität ist standardmäßig nur für Projekte aktiviert, die für `net5.0` oder höher entwickelt werden. Sie können es jedoch auch für Projekte [aktivieren](/visualstudio/code-quality/ca1416.md#configurability), die auf andere Frameworks abzielen.

## <a name="how-the-analyzer-determines-platform-dependency"></a>Bestimmen der Plattformabhängigkeit mithilfe des Analysetools

- Bei einer **nicht attributierten API** wird davon ausgegangen, dass sie auf **allen Betriebssystemplattformen** funktioniert.
- Eine API, die mit `[SupportedOSPlatform("platform")]` gekennzeichnet ist, gilt als nur für das angegebene Betriebssystem (`platform`) portierbar.
  - Das Attribut kann mehrmals angewendet werden, um **Unterstützung für mehrere Plattformen** anzugeben (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).
  - Das Analysetool generiert eine **Warnung**, wenn ohne einen ordnungsgemäßen **Plattformkontext** auf plattformspezifische APIs verwiesen wird:
    - **Warnung**, wenn das Projekt nicht auf die unterstützte Plattform ausgerichtet ist (z. B. bei einem Windows-spezifischen API-Aufruf, wenn das Projekt auf `<TargetFramework>net5.0-ios14.0</TargetFramework>` abzielt)
    - **Warnung**, wenn das Projekt auf mehrere Zielanwendungen ausgerichtet ist (`<TargetFramework>net5.0</TargetFramework>`)
    - **Keine Warnung**, wenn innerhalb eines Projekts auf die plattformspezifische API verwiesen wird, das auf eine der **angegebenen Plattformen** ausgerichtet ist (z. B. bei einem Windows-spezifischen API-Aufruf, wenn das Projekt auf `<TargetFramework>net5.0-windows</TargetFramework>` abzielt)
    - **Keine Warnung**, wenn der plattformspezifische API-Aufruf durch entsprechende Plattformprüfmethoden geschützt wird (z. B. `if(OperatingSystem.IsWindows())`)
    - **Keine Warnung**, wenn aus dem gleichen plattformspezifischen Kontext auf die plattformspezifische API verwiesen wird (**Aufrufort auch attributiert** mit `[SupportedOSPlatform("platform")`)
- Eine API, die mit `[UnsupportedOSPlatform("platform")]` gekennzeichnet ist, gilt nur unter dem angegebenen Betriebssystem (`platform`) als nicht unterstützt, unter allen anderen Plattformen als unterstützt.
  - Das Attribut kann mehrmals für verschiedene Plattformen angewendet werden, z. B. `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.
  - Das Analysetool generiert nur dann eine **Warnung**, wenn `platform` für den gesamten Aufrufort gilt:
    - **Warnung**, wenn das Projekt auf die Plattform ausgerichtet ist, die laut Attribut nicht unterstützt wird (z. B. bei einer mit `[UnsupportedOSPlatform("windows")]` attributierten API, wenn der Aufrufort auf `<TargetFramework>net5.0-windows</TargetFramework>` abzielt)
    - **Warnung**, wenn das Projekt auf mehrere Frameworks abzielt und `platform` in der Standardelementgruppe [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) enthalten ist oder manuell in die Elementgruppe `MSBuild` \<SupportedPlatform> eingefügt wird:

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - **Keine Warnung**, wenn Sie eine App erstellen, die nicht auf die nicht unterstützte Plattform oder mehrere Zielplattform ausgerichtet ist, und die Plattform nicht in der Standardelementgruppe [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) enthalten ist
- Beide Attribute können mit oder ohne Versionsnummern als Teil des Plattformnamens instanziiert werden.
  - Versionsnummern weisen das Format `major.minor[.build[.revision]]` auf. `major.minor` ist erforderlich, die Teile `build` und `revision` sind optional. „Windows7.0“ gibt z. B. die Windows-Version 7.0 an, „Windows“ wird jedoch wie „Windows 0.0“ interpretiert.

Weitere Informationen finden Sie unter [Beispiele für die Funktionsweise von Attributen und ihre Diagnosen](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).

### <a name="advanced-scenarios-for-combining-attributes"></a>Erweiterte Szenarios für die Kombination von Attributen

- Wenn eine Kombination der Attribute `[SupportedOSPlatform]` und `[UnsupportedOSPlatform]` vorliegt, werden alle Attribute nach dem Bezeichner der Betriebssystemplattform gruppiert:
  - **Liste mit ausschließlich unterstützten Plattformen:** Wenn die niedrigste Version jeder Betriebssystemplattform das Attribut `[SupportedOSPlatform]` aufweist, gilt die API als nur von den aufgelisteten Plattformen unterstützt und für alle anderen Plattformen als nicht unterstützt. Die optionalen `[UnsupportedOSPlatform]`-Attribute für die einzelnen Plattform können nur eine höhere Version der unterstützten Mindestversion aufweisen, was bedeutet, dass die API-Unterstützung ab der angegebenen Version entfernt wird.

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - **Liste mit ausschließlich nicht unterstützten Plattformen:** Wenn die niedrigste Version jeder Betriebssystemplattform das Attribut `[UnsupportedOSPlatform]` aufweist, gilt die API als nur von den aufgelisteten Plattformen nicht unterstützt und für alle anderen Plattformen als unterstützt. Die Liste kann das Attribut `[SupportedOSPlatform]` für die gleiche Plattform, aber eine höhere Version aufweisen, was bedeutet, dass die API ab dieser Version unterstützt wird.
  
    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - **Inkonsistente Liste:** Wenn die niedrigste Version für einige Plattformen das Attribut `[SupportedOSPlatform]`, für andere Plattformen jedoch das Attribut `[UnsupportedOSPlatform]` aufweist, wird die Liste als inkonsistent eingestuft. Dies wird vom Analysetool nicht unterstützt.
  - Wenn die niedrigsten Versionen der Attribute `[SupportedOSPlatform]` und `[UnsupportedOSPlatform]` gleich sind, gilt die Plattform für das Analysetool als Teil der **Liste mit ausschließlich unterstützten Plattformen**.
- Plattformattribute können auf Typen, Member (Methoden, Felder, Eigenschaften und Ereignisse) und Assemblys mit einem anderen Plattformnamen und/oder einer anderen Version angewendet werden.
  - Attribute, die auf das oberste Ziel (`target`) angewendet werden, gelten infolge auch für alle Member und Typen.
  - Untergeordnete Attribute gelten nur, wenn sie die Regel „Untergeordnete Attribute können die Plattformunterstützung nur einschränken, nicht erweitern“ befolgen.
    - Wenn das übergeordnete Element eine **Liste mit ausschließlich unterstützten Plattformen** aufweist, können die untergeordneten Memberattribute keine neue Plattformunterstützung hinzufügen, da dies die Unterstützung für das übergeordnete Element erweitern würde. Neue Plattformunterstützung kann jedoch nur dem übergeordneten Element selbst hinzugefügt werden. Die Memberattribute können jedoch das Attribut `Supported` für dieselbe Plattform mit höheren Versionen aufweisen, da dies die Unterstützung einschränken würde. Sie können außerdem das Attribut `Unsupported` für dieselbe Plattform aufweisen, das auch dies die übergeordnete Unterstützung eingrenzen würde.
    - Wenn das übergeordnete Element eine **Liste mit ausschließlich nicht unterstützten Plattformen** aufweist, können die untergeordneten Memberattribute neue Plattformunterstützung hinzufügen, da die übergeordnete Unterstützung eingeschränkt werden würde. Die Memberattribute können jedoch nicht das Attribut `Supported` für dieselbe Plattform wie im übergeordneten Element aufweisen, da dies die übergeordnete Unterstützung erweitern würde. Unterstützung für dieselbe Plattform kann nur auf übergeordneter Ebene hinzugefügt werden, auf der das ursprüngliche `Unsupported`-Attribut angewendet wurde.
  - Wenn `[SupportedOSPlatform("platformVersion")]` mehr als einmal auf eine API mit demselben `platform`-Namen angewendet wird, wird nur diejenige mit der Mindestversion vom Analysetool berücksichtigt.
  - Wenn `[UnsupportedOSPlatform("platformVersion")]` mehr als zweimal auf eine API mit demselben `platform`-Namen angewendet wird, werden nur die beiden mit der frühesten Version vom Analysetool berücksichtigt.
  
  > [!NOTE]
  > Wenn die Unterstützung für eine API zunächst vorhanden war und in einer höheren Version abgeschafft wurde, wird sie erwartungsgemäß in einer noch höheren Version nicht wieder eingeführt.

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a>Beispiele für die Funktionsweise von Attributen und ihre Diagnosen

  ```csharp
  // An API supported only on Windows.
  [SupportedOSPlatform("Windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  public void Caller()
  {
      WindowsOnlyApi(); // warns: 'WindowsOnlyApi' is supported on 'windows'

      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Windows'
      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Linux'
      SupportedOnWindowsAndLinuxOnly();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 8.0 and later  
      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // for same platform analyzer only warn for the latest version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  public void Caller2()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'android'

      // warns:'StartedWindowsSupportFromVersion8' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFromVersion8' is supported on 'windows' 8.0 and later
      StartedWindowsSupportFromVersion8();

      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is supported on 'windows' 8.0 and later
      // even there were 3 diagnostics found analyzer warn only for the first 2.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

## <a name="handle-reported-warnings"></a>Verarbeiten gemeldeter Warnungen

Die empfohlene Umgangsweise mit diesen Diagnosen besteht darin, sicherzustellen, dass plattformspezifische APIs nur auf der passenden Plattform aufgerufen werden. Nachstehend sind Ihre Optionen für die Behebung dieser Warnungen aufgeführt. Wählen Sie die Vorgehensweise aus, die sich am besten für Ihre Situation eignet:

- **Schützen des Aufrufs:** Zu diesem Zweck können Sie den Code bedingt zur Laufzeit aufrufen. Überprüfen Sie, ob die Ausführung unter einem gewünschten Betriebssystem (`Platform`) erfolgt, indem Sie eine der Plattformprüfmethoden verwenden, z. B. `OperatingSystem.Is<Platform>()` oder `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.

- **Markieren des Aufruforts als plattformspezifisch:** Sie können auch Ihre eigenen APIs als plattformspezifisch kennzeichnen und die Anforderungen so effektiv an Ihre Aufrufer weiterleiten. Kennzeichnen Sie die enthaltende Methode, den enthaltenden Typ oder die gesamte Assembly mit denselben Attributen wie den referenzierten plattformabhängigen Aufruf. [Beispiele](#mark-call-site-as-platform-specific).

- **Bestätigen des Aufruforts mit einer Plattformüberprüfung:** Wenn Sie den Mehraufwand einer zusätzlichen `if`-Anweisung zur Laufzeit vermeiden möchten, verwenden Sie <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>. [Beispiel](#assert-the-call-site-with-platform-check).

- **Löschen des Codes:** Dies ist üblicherweise nicht die gewünschte Vorgehensweise, da Sie möglicherweise Kunden verlieren, wenn Ihr Code von Windows-Benutzern verwendet wird. Falls eine plattformübergreifende Alternative vorhanden ist, sollten Sie lieber diese anstelle der plattformspezifischen APIs wählen.

- **Unterdrücken der Warnung:** Sie können die Warnung auch einfach unterdrücken, entweder über „editor.config“ oder `#pragma warning disable ca1416`. Diese Option sollte jedoch bei der Verwendung von plattformspezifischen APIs als allerletzte Maßnahme eingesetzt werden.

### <a name="guard-platform-specific-apis-with-guard-methods"></a>Schützen von plattformspezifischen APIs mit Schutzmethoden

Der Plattformname der Schutzmethode muss mit dem aufrufenden plattformabhängigen API-Plattformnamen übereinstimmen. Wenn die Plattformzeichenfolge der aufrufenden API die Version enthält:

- muss die Plattformversion (`version`) der Schutzmethode für das Attribut `[SupportedOSPlatform("platformVersion")]` größer oder gleich der `Version` der aufrufenden Plattform sein
- muss die Plattformversion (`version`) der Schutzmethode für das Attribut `[UnsupportedOSPlatform("platformVersion")]` kleiner oder gleich der `Version` der aufrufenden Plattform sein

  ```csharp
  public void CallingSupportedOnlyApis() // Allow list calls
  {
      if (OperatingSystem.IsWindows())
      {
          WindowsOnlyApi(); // will not warn
      }

      if (OperatingSystem.IsLinux())
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn, within one of the supported context
      }

      // Can use &&, || logical operators to guard combined attributes
      if (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10.0.19041)))
      {
          ApiSupportedFromWindows8UnsupportFromWindows10();
      }

      if (OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903))
      {
          AssemblySupportedOnWindowsApiSupportedFromWindows10(); // Only need to check latest supported version
      }
  }

  public void CallingUnsupportedApis()
  {
      if (!OperatingSystem.IsAndroid())
      {
          DoesNotWorkOnAndroid(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || OperatingSystem.IsWindowsVersionAtLeast(8))
      {
          StartedWindowsSupportFromVersion8(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || // supported all other platforms
         (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903)))
      {
          StartedWindowsSupportFrom8UnsupportedFrom10(); // will not warn
      }
  }
  ```

- und Code geschützt werden muss, der auf netstandard oder netcoreapp ausgerichtet ist, wo keine neuen <xref:System.OperatingSystem>-APIs verfügbar sind, kann die API <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> verwendet werden. Diese wird auch vom Analysetool berücksichtigt. Sie ist jedoch nicht so optimiert, wie die neuen APIs, die über <xref:System.OperatingSystem> hinzugefügt werden. Falls die Plattform in der Struktur <xref:System.Runtime.InteropServices.OSPlatform> nicht unterstützt wird, können Sie die Methode <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType>("platform") verwenden, die auch vom Analysetool berücksichtigt wird.

  ```csharp
  public void CallingSupportedOnlyApis()
  {
      if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn
      }

      if (RuntimeInformation.IsOSPlatform(OSPlatform.Create("browser")))
      {
          ApiOnlySupportedOnBrowser(); // call of browser specific API
      }
  }
  ```

### <a name="mark-call-site-as-platform-specific"></a>Markieren des Aufruforts als plattformspezifisch

Plattformnamen sollten mit der aufrufenden plattformabhängigen API übereinstimmen. Wenn die Plattformzeichenfolge eine Version enthält:

- muss die Plattformversion (`version`) des Aufruforts für das Attribut `[SupportedOSPlatform("platformVersion")]` größer oder gleich der `Version` der aufrufenden Plattform sein
- muss die Plattformversion (`version`) des Aufruforts für das Attribut `[UnsupportedOSPlatform("platformVersion")]` kleiner oder gleich der `Version` der aufrufenden Plattform sein

  ```csharp
  // an API supported only on Windows.
  [SupportedOSPlatform("windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  [SupportedOSPlatform("windows8.0")] // call site attributed Windows 8.0 or above.
  public void Caller()
  {
      WindowsOnlyApi(); // will not warn as call site is for Windows.

      // will not warn as call site is for Windows.
      SupportedOnWindowsAndLinuxOnly();

      // will not warn for the API's [SupportedOSPlatform("windows8.0")] attribute.
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // as the call site version is lower than calling version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows11.0")] // call site attributed with windows 11.0 or above.
  public void Caller2()
  {
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // will not warn as call site version higher than calling API.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")] // call site supports Windows from version 8.0 to 10.0.19041.0.
  public void Caller3()
  {
      // will not warn as caller has exact same attributes.
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // As call site stopped support from that version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on Android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  [UnsupportedOSPlatform("windows")] // Caller no support Windows for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'Android'.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }

  [UnsupportedOSPlatform("windows")]
  [UnsupportedOSPlatform("android")] // Caller not support Windows and Android for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // will not warn as call site not supports Android.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

### <a name="assert-the-call-site-with-platform-check"></a>Bestätigen des Aufruforts mit einer Plattformüberprüfung

Alle in den [Beispielen für den Plattformschutz](#guard-platform-specific-apis-with-guard-methods) verwendeten bedingten Überprüfungen können auch als Bedingung in <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> eingefügt werden.

  ```csharp
  // An API supported only on Linux.
  [SupportedOSPlatform("linux")]
  public void LinuxOnlyApi() { }

  public void Caller()
  {
      Debug.Assert(OperatingSystem.IsLinux());

      LinuxOnlyApi(); // will not warn
  }
  ```

## <a name="see-also"></a>Weitere Informationen

- [Namen von Zielframeworks in .NET 5](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [Kommentieren von plattformspezifischen APIs und Erkennen der Verwendung](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [Annotieren von APIs als nicht unterstützt auf bestimmten Plattformen](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [CA1416: Analysetool für die Plattformkompatibilität](/visualstudio/code-quality/ca1416)
- [.NET API-Analysetool](../../standard/analyzers/api-analyzer.md)
