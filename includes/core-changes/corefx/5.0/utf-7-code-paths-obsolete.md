---
ms.openlocfilehash: 1cb6e953aa57c72ee6a2665c521bada10e0786cf
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455772"
---
### <a name="utf-7-code-paths-are-obsolete"></a><span data-ttu-id="4e066-101">UTF-7-Codepfade sind veraltet</span><span class="sxs-lookup"><span data-stu-id="4e066-101">UTF-7 code paths are obsolete</span></span>

<span data-ttu-id="4e066-102">Die UTF-7-Codierung wird in Anwendungen kaum noch verwendet, und viele Spezifikationen [verbieten ihre Verwendung](https://security.stackexchange.com/a/68609/3573) im Austausch.</span><span class="sxs-lookup"><span data-stu-id="4e066-102">The UTF-7 encoding is no longer in wide use among applications, and many specs now [forbid its use](https://security.stackexchange.com/a/68609/3573) in interchange.</span></span> <span data-ttu-id="4e066-103">Sie wird zuweilen auch in Anwendungen, die keine UTF-7-codierten Daten erwarten, [als Angriffsvektor verwendet](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7).</span><span class="sxs-lookup"><span data-stu-id="4e066-103">It's also occasionally [used as an attack vector](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) in applications that don't anticipate encountering UTF-7-encoded data.</span></span> <span data-ttu-id="4e066-104">Microsoft warnt vor der Verwendung von <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>, weil es keine Fehlererkennung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4e066-104">Microsoft warns against use of <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> because it doesn't provide error detection.</span></span>

<span data-ttu-id="4e066-105">Folglich sind die <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>-Eigenschaft und der <xref:System.Text.UTF7Encoding.%23ctor%2A>-Konstruktor jetzt ebenfalls veraltet.</span><span class="sxs-lookup"><span data-stu-id="4e066-105">Consequently, the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property and <xref:System.Text.UTF7Encoding.%23ctor%2A> constructors are now obsolete.</span></span> <span data-ttu-id="4e066-106">Darüber hinaus erlauben <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> und <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> nicht mehr die Angabe von `UTF-7`.</span><span class="sxs-lookup"><span data-stu-id="4e066-106">Additionally, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> and <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> no longer allow you to specify `UTF-7`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4e066-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4e066-107">Change description</span></span>

<span data-ttu-id="4e066-108">Bisher konnten Sie mithilfe der <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>-APIs eine Instanz der UTF-7-Codierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e066-108">Previously, you could create an instance of the UTF-7 encoding by using the <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> APIs.</span></span> <span data-ttu-id="4e066-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4e066-109">For example:</span></span>

```csharp
Encoding enc1 = Encoding.GetEncoding("utf-7"); // By name.
Encoding enc2 = Encoding.GetEncoding(65000); // By code page.
```

<span data-ttu-id="4e066-110">Darüber hinaus wurde eine Instanz, die die UTF-7-Codierung repräsentiert, durch die <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType>-Methode enumeriert, wodurch alle im System registrierten <xref:System.Text.Encoding>-Instanzen enumeriert wurden.</span><span class="sxs-lookup"><span data-stu-id="4e066-110">Additionally, an instance that represents the UTF-7 encoding was enumerated by the <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> method, which enumerates all the <xref:System.Text.Encoding> instances registered on the system.</span></span>

<span data-ttu-id="4e066-111">Ab .NET 5.0 sind die <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>-Eigenschaft und die <xref:System.Text.UTF7Encoding.%23ctor%2A>-Konstruktoren veraltet und erzeugen die Warnung `SYSLIB0001` (bzw. `MSLIB0001` in Vorschauversionen).</span><span class="sxs-lookup"><span data-stu-id="4e066-111">Starting in .NET 5.0, the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property and <xref:System.Text.UTF7Encoding.%23ctor%2A> constructors are obsolete and produce warning `SYSLIB0001` (or `MSLIB0001` in preview versions).</span></span> <span data-ttu-id="4e066-112">Um jedoch die Anzahl von Warnungen zu reduzieren, die Aufrufer bei Verwendung der <xref:System.Text.UTF7Encoding>-Klasse empfangen, wurde der <xref:System.Text.UTF7Encoding>-Typ selbst nicht als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="4e066-112">However, to reduce the number of warnings that callers receive when using the <xref:System.Text.UTF7Encoding> class, the <xref:System.Text.UTF7Encoding> type itself is not marked obsolete.</span></span>

```csharp
// The next line generates warning SYSLIB0001.
UTF7Encoding enc = new UTF7Encoding();
// The next line does not generate a warning.
byte[] bytes = enc.GetBytes("Hello world!");
```

<span data-ttu-id="4e066-113">Darüber hinaus behandeln die <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>-Methoden den Codierungsnamen `utf-7` und die Codepage `65000` als `unknown`.</span><span class="sxs-lookup"><span data-stu-id="4e066-113">Additionally, the <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> methods treat the encoding name `utf-7` and the code page `65000` as `unknown`.</span></span> <span data-ttu-id="4e066-114">Da die Codierung als `unknown` behandelt wird, löst die Methode eine <xref:System.ArgumentException> aus.</span><span class="sxs-lookup"><span data-stu-id="4e066-114">Treating the encoding as `unknown` causes the method to throw an <xref:System.ArgumentException>.</span></span>

```csharp
// Throws ArgumentException, same as calling Encoding.GetEncoding("unknown").
Encoding enc = Encoding.GetEncoding("utf-7");
```

<span data-ttu-id="4e066-115">Außerdem schließt die <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType>-Methode die UTF-7-Codierung nicht in das von ihr zurückgegebene <xref:System.Text.EncodingInfo>-Array ein.</span><span class="sxs-lookup"><span data-stu-id="4e066-115">Finally, the <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> method doesn't include the UTF-7 encoding in the <xref:System.Text.EncodingInfo> array that it returns.</span></span> <span data-ttu-id="4e066-116">Die Codierung wird ausgeschlossen, weil sie nicht instanziiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e066-116">The encoding is excluded because it cannot be instantiated.</span></span>

```csharp
foreach (EncodingInfo encInfo in Encoding.GetEncodings())
{
    // The next line would throw if GetEncodings included UTF-7.
    Encoding enc = Encoding.GetEncoding(encInfo.Name);
}
```

#### <a name="reason-for-change"></a><span data-ttu-id="4e066-117">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="4e066-117">Reason for change</span></span>

<span data-ttu-id="4e066-118">Viele Anwendungen rufen `Encoding.GetEncoding("encoding-name")` mit einem Wert für den Codierungsnamen auf, der von einer nicht vertrauenswürdigen Quelle bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4e066-118">Many applications call `Encoding.GetEncoding("encoding-name")` with an encoding name value that's provided by an untrusted source.</span></span> <span data-ttu-id="4e066-119">Beispielsweise könnte ein Webclient oder Webserver den `charset`-Teil des `Content-Type`-Headers verwenden und den Wert direkt an `Encoding.GetEncoding` übergeben, ohne ihn zu validieren.</span><span class="sxs-lookup"><span data-stu-id="4e066-119">For example, a web client or server might take the `charset` portion of the `Content-Type` header and pass the value directly to `Encoding.GetEncoding` without validating it.</span></span> <span data-ttu-id="4e066-120">So könnte ein schädlicher Endpunkt `Content-Type: ...; charset=utf-7` angeben, was zu einem unerwünschten Verhalten bei der empfangenden Anwendung führen könnte.</span><span class="sxs-lookup"><span data-stu-id="4e066-120">This could allow a malicious endpoint to specify `Content-Type: ...; charset=utf-7`, which could cause the receiving application to misbehave.</span></span>

<span data-ttu-id="4e066-121">Darüber hinaus ermöglicht die Deaktivierung von UTF-7-Codepfaden es Optimierungscompilern, wie beispielsweise denen von Blazor, diese Codepfade vollständig aus der resultierenden Anwendung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4e066-121">Additionally, disabling UTF-7 code paths allows optimizing compilers, such as those used by Blazor, to remove these code paths entirely from the resulting application.</span></span> <span data-ttu-id="4e066-122">Im Ergebnis werden die kompilierten Anwendungen effizienter ausgeführt und belegen weniger Speicherplatz auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="4e066-122">As a result, the compiled applications run more efficiently and take less disk space.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4e066-123">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="4e066-123">Version introduced</span></span>

<span data-ttu-id="4e066-124">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="4e066-124">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4e066-125">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="4e066-125">Recommended action</span></span>

<span data-ttu-id="4e066-126">In denen meisten Fällen müssen Sie keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="4e066-126">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="4e066-127">Wenn Sie jedoch über Apps verfügen, in denen zuvor UTF-7-bezogene Codepfade aktiviert waren, sollten Sie sich die folgende Anleitung ansehen.</span><span class="sxs-lookup"><span data-stu-id="4e066-127">However, for apps that have previously activated UTF-7-related code paths, consider the guidance that follows.</span></span>

- <span data-ttu-id="4e066-128">Wenn Ihre App <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> mit unbekannten Codierungsnamen aufruft, die aus einer nicht vertrauenswürdigen Quelle stammen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4e066-128">If your app calls <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> with unknown encoding names provided by an untrusted source:</span></span>

  <span data-ttu-id="4e066-129">Vergleichen Sie stattdessen die Codierungsnamen mit einer konfigurierbaren Zulassungsliste.</span><span class="sxs-lookup"><span data-stu-id="4e066-129">Instead, compare the encoding names against a configurable allow list.</span></span> <span data-ttu-id="4e066-130">Die konfigurierbare Zulassungsliste sollte mindestens den Branchenstandard „UTF-8“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="4e066-130">The configurable allow list should at minimum include the industry-standard "utf-8".</span></span> <span data-ttu-id="4e066-131">Je nach vorhandenen Clients und gesetzlichen Anforderungen müssen möglicherweise auch regionsspezifische Codierungen zulassen, wie z. B. „GB18030“.</span><span class="sxs-lookup"><span data-stu-id="4e066-131">Depending on your clients and regulatory requirements, you may also need to allow region-specific encodings, such as "GB18030".</span></span>

  <span data-ttu-id="4e066-132">Wenn Sie keine Zulassungsliste implementieren, gibt <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> jede <xref:System.Text.Encoding> zurück, die im System integriert ist oder über einen benutzerdefinierten <xref:System.Text.EncodingProvider> registriert ist.</span><span class="sxs-lookup"><span data-stu-id="4e066-132">If you don't implement an allow list, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> will return any <xref:System.Text.Encoding> that's built into the system or that's registered via a custom <xref:System.Text.EncodingProvider>.</span></span> <span data-ttu-id="4e066-133">Überprüfen Sie die Anforderungen Ihres Diensts, um sich zu vergewissern, dass dies das gewünschte Verhalten ist.</span><span class="sxs-lookup"><span data-stu-id="4e066-133">Audit your service's requirements to validate that this is the desired behavior.</span></span> <span data-ttu-id="4e066-134">UTF-7 ist weiterhin standardmäßig deaktiviert, es sei denn, Ihre Anwendung aktiviert den Kompatibilitätsschalter wieder, der weiter unten in diesem Artikel beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4e066-134">UTF-7 continues to be disabled by default unless your application re-enables the compatibility switch mentioned later in this article.</span></span>

- <span data-ttu-id="4e066-135">Wenn Sie <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> oder <xref:System.Text.UTF7Encoding> in Ihrem eigenen Protokoll oder Dateiformat verwenden, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="4e066-135">If you're using <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding> within your own protocol or file format:</span></span>

  <span data-ttu-id="4e066-136">Wechseln Sie zu <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> oder <xref:System.Text.UTF8Encoding>.</span><span class="sxs-lookup"><span data-stu-id="4e066-136">Switch to using <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> or <xref:System.Text.UTF8Encoding>.</span></span> <span data-ttu-id="4e066-137">UTF-8 ist ein Branchenstandard und wird über Sprachen, Betriebssysteme und Runtimes hinweg flächendeckend unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e066-137">UTF-8 is an industry standard and is widely supported across languages, operating systems, and runtimes.</span></span> <span data-ttu-id="4e066-138">Die Verwendung von UTF-8 vereinfacht die zukünftige Wartung Ihres Codes und sorgt für mehr Interoperabilität mit dem Rest des Ökosystems.</span><span class="sxs-lookup"><span data-stu-id="4e066-138">Using UTF-8 eases future maintenance of your code and makes it more interoperable with the rest of the ecosystem.</span></span>

- <span data-ttu-id="4e066-139">Wenn Sie eine <xref:System.Text.Encoding>-Instanz mit <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> vergleichen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="4e066-139">If you're comparing an <xref:System.Text.Encoding> instance against <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span></span>

  <span data-ttu-id="4e066-140">Erwägen Sie stattdessen eine Überprüfung anhand der bekannten UTF-7-Codepage, die `65000` lautet.</span><span class="sxs-lookup"><span data-stu-id="4e066-140">Instead, consider performing a check against the well-known UTF-7 code page, which is `65000`.</span></span> <span data-ttu-id="4e066-141">Durch Vergleichen mit der Codepage vermeiden Sie die Warnung und können außerdem einige Sonderfälle behandeln, wenn beispielsweise jemand `new UTF7Encoding()` aufgerufen oder Unterklassen des Typs erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="4e066-141">By comparing against the code page, you avoid the warning and also handle some edge cases, such as if somebody called `new UTF7Encoding()` or subclassed the type.</span></span>

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

- <span data-ttu-id="4e066-142">Wenn Sie <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> oder <xref:System.Text.UTF7Encoding>verwenden müssen, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4e066-142">If you must use <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding>:</span></span>

  <span data-ttu-id="4e066-143">Sie können die `SYSLIB0001`-Warnung im Code oder in der *CSPROJ*-Datei Ihres Projekts unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="4e066-143">You can suppress the `SYSLIB0001` warning in code or within your project's *.csproj* file.</span></span>

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
  > <span data-ttu-id="4e066-144">Das Unterdrücken von `SYSLIB0001` deaktiviert nur die Warnungen, dass <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> und <xref:System.Text.UTF7Encoding> veraltet sind.</span><span class="sxs-lookup"><span data-stu-id="4e066-144">Suppressing `SYSLIB0001` only disables the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> and <xref:System.Text.UTF7Encoding> obsoletion warnings.</span></span> <span data-ttu-id="4e066-145">Andere Warnungen werden nicht deaktiviert, und das Verhalten von APIs wie <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="4e066-145">It doesn't disable any other warnings or change the behavior of APIs like <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="4e066-146">Wenn Sie `Encoding.GetEncoding("utf-7", ...)` unterstützen müssen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4e066-146">If you must support `Encoding.GetEncoding("utf-7", ...)`:</span></span>

  <span data-ttu-id="4e066-147">Sie können die Unterstützung über einen Kompatibilitätsschalter wieder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4e066-147">You can re-enable support for this via a compatibility switch.</span></span> <span data-ttu-id="4e066-148">Dieser Kompatibilitätsschalter kann in der *CSPROJ*-Datei der Anwendung oder in einer [Runtimekonfigurationsdatei](../../../../docs/core/run-time-config/index.md) angegeben werden, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e066-148">This compatibility switch can be specified in the application's *.csproj* file or in a [run-time configuration file](../../../../docs/core/run-time-config/index.md), as shown in the following examples.</span></span>

  <span data-ttu-id="4e066-149">In der *CSPROJ*-Datei der Anwendung:</span><span class="sxs-lookup"><span data-stu-id="4e066-149">In the application's *.csproj* file:</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- Re-enable support for UTF-7 -->
     <EnableUnsafeUTF7Encoding>true</EnableUnsafeUTF7Encoding>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="4e066-150">In der *runtimeconfig.template.json*-Datei der Anwendung:</span><span class="sxs-lookup"><span data-stu-id="4e066-150">In the application's *runtimeconfig.template.json* file:</span></span>

  ```json
  {
    "configProperties": {
      "System.Text.Encoding.EnableUnsafeUTF7Encoding": true
    }
  }
  ```

  > [!TIP]
  > <span data-ttu-id="4e066-151">Wenn Sie die Unterstützung für UTF-7 wieder aktivieren, sollten Sie eine Sicherheitsüberprüfung des Codes durchführen, der <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> aufruft.</span><span class="sxs-lookup"><span data-stu-id="4e066-151">If you re-enable support for UTF-7, you should perform a security review of code that calls <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="4e066-152">Kategorie</span><span class="sxs-lookup"><span data-stu-id="4e066-152">Category</span></span>

- <span data-ttu-id="4e066-153">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="4e066-153">Core .NET libraries</span></span>
- <span data-ttu-id="4e066-154">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4e066-154">Security</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4e066-155">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4e066-155">Affected APIs</span></span>

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
