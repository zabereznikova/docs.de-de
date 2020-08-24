---
ms.openlocfilehash: 7cb146d19486618a4cee9976abe2220ea4b72790
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "88204017"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a><span data-ttu-id="ef922-101">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="ef922-101">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>

<span data-ttu-id="ef922-102">`Serialize`- und `Deserialize`-Methoden in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> und <xref:System.Runtime.Serialization.IFormatter> sind jetzt veraltet.</span><span class="sxs-lookup"><span data-stu-id="ef922-102">`Serialize` and `Deserialize` methods on <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter>, and <xref:System.Runtime.Serialization.IFormatter> are now obsolete.</span></span> <span data-ttu-id="ef922-103">Darüber hinaus ist die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Serialisierung in ASP.NET-Apps standardmäßig verboten.</span><span class="sxs-lookup"><span data-stu-id="ef922-103">Additionally, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is prohibited by default for ASP.NET apps.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ef922-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ef922-104">Change description</span></span>

<span data-ttu-id="ef922-105">Aufgrund von [Sicherheitsrisiken](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> sind die folgenden Methoden jetzt veraltet.</span><span class="sxs-lookup"><span data-stu-id="ef922-105">Due to [security vulnerabilities](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following methods are now obsolete.</span></span> <span data-ttu-id="ef922-106">Darüber hinaus wird <xref:System.NotSupportedException> in ASP.NET Core 5.0-Apps (und höher)ausgelöst, es sei denn, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> wurde durch die Web-App wieder aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef922-106">Additionally, in ASP.NET Core 5.0 and later apps, they will throw a <xref:System.NotSupportedException>, unless the web app has re-enabled <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> functionality.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

<span data-ttu-id="ef922-107">Diese Methoden wurden im Rahmen unsere Bemühungen als veraltet markiert, die Nutzung von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> im .NET-Ökosystem einzudämmen.</span><span class="sxs-lookup"><span data-stu-id="ef922-107">These methods are marked obsolete as part of an effort to wind down usage of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> within the .NET ecosystem.</span></span>

<span data-ttu-id="ef922-108">Die folgenden Serialisierungsmethoden sind jetzt ebenfalls veraltet, führen jedoch nicht zu Änderungen im Verhalten:</span><span class="sxs-lookup"><span data-stu-id="ef922-108">The following serialization methods are also now obsolete, but have no behavioral changes:</span></span>

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a><span data-ttu-id="ef922-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ef922-109">Version introduced</span></span>

<span data-ttu-id="ef922-110">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="ef922-110">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ef922-111">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ef922-111">Recommended action</span></span>

- <span data-ttu-id="ef922-112">Verwenden Sie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> nicht mehr in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ef922-112">Stop using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in your code.</span></span> <span data-ttu-id="ef922-113">Verwenden Sie stattdessen <xref:System.Text.Json.JsonSerializer> oder <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ef922-113">Instead, consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="ef922-114">Weitere Informationen finden Sie im [BinaryFormatter-Sicherheitsleitfaden](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="ef922-114">For more information, see [BinaryFormatter security guide](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span></span>

- <span data-ttu-id="ef922-115">Sie können vorübergehend die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Warnung zur Kompilierzeit unterdrücken, die `SYSLIB0011` lautet.</span><span class="sxs-lookup"><span data-stu-id="ef922-115">You can temporarily suppress the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> compile-time warning, which is `SYSLIB0011`.</span></span> <span data-ttu-id="ef922-116">Es empfiehlt sich, Ihren Code gründlich auf Risiken zu untersuchen, bevor Sie sich für diese Option entscheiden.</span><span class="sxs-lookup"><span data-stu-id="ef922-116">We recommend that you thoroughly assess your code for risks before choosing this option.</span></span> <span data-ttu-id="ef922-117">Die Warnungen lassen sich am einfachsten unterdrücken, indem Sie die einzelne Aufrufsite mit `#pragma`-Anweisungen umschließen.</span><span class="sxs-lookup"><span data-stu-id="ef922-117">The easiest way to suppress the warnings is to surround the individual call site with `#pragma` directives.</span></span>

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  <span data-ttu-id="ef922-118">Sie können die Warnung auch in der Projektdatei unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="ef922-118">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  <span data-ttu-id="ef922-119">Wenn Sie die Warnung in der Projektdatei unterdrücken, wird sie für alle Codedateien im Projekt unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="ef922-119">If you suppress the warning in the project file, the warning is suppressed for all code files in the project.</span></span> <span data-ttu-id="ef922-120">Durch Unterdrücken von SYSLIB0011 werden keine Warnungen unterdrückt, die von anderen veralteten APIs verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="ef922-120">Suppressing SYSLIB0011 does not suppress warnings caused by using other obsolete APIs.</span></span>

- <span data-ttu-id="ef922-121">Um <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> weiterhin in ASP.NET-Apps zu verwenden, können Sie die Option in der Projektdatei wieder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ef922-121">To continue using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in ASP.NET apps, you can re-enable it in the project file.</span></span> <span data-ttu-id="ef922-122">Es wird jedoch dringend empfohlen, dies nicht zu tun.</span><span class="sxs-lookup"><span data-stu-id="ef922-122">However, it's strongly recommended not to do this.</span></span> <span data-ttu-id="ef922-123">Weitere Informationen finden Sie im [BinaryFormatter-Sicherheitsleitfaden](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="ef922-123">For more information, see [BinaryFormatter security guide](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span></span>

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

<span data-ttu-id="ef922-124">Weitere Informationen zu empfohlenen Aktionen finden Sie unter [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter) (Auflösen von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter).</span><span class="sxs-lookup"><span data-stu-id="ef922-124">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

#### <a name="category"></a><span data-ttu-id="ef922-125">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ef922-125">Category</span></span>

- <span data-ttu-id="ef922-126">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ef922-126">Core .NET libraries</span></span>
- <span data-ttu-id="ef922-127">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ef922-127">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ef922-128">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ef922-128">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
