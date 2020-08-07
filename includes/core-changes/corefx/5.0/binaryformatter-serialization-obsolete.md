---
ms.openlocfilehash: c5204e8c80cb737338b053c39083c0cc43786447
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517326"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a>BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten

`Serialize`- und `Deserialize`-Methoden in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> und <xref:System.Runtime.Serialization.IFormatter> sind jetzt veraltet. Darüber hinaus ist die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Serialisierung in ASP.NET-Apps standardmäßig verboten.

#### <a name="change-description"></a>Änderungsbeschreibung

Aufgrund von [Sicherheitsrisiken](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> sind die folgenden Methoden jetzt veraltet. Darüber hinaus lösen sie in Apps mit ASP.NET 5.0 oder höher eine <xref:System.NotSupportedException> aus, es sei denn, die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Funktionalität wurde durch die Web-App wieder aktiviert.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

Diese Methoden wurden im Rahmen unsere Bemühungen als veraltet markiert, die Nutzung von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> im .NET-Ökosystem einzudämmen.

Die folgenden Serialisierungsmethoden sind jetzt ebenfalls veraltet, führen jedoch nicht zu Änderungen im Verhalten:

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

- Verwenden Sie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> nicht mehr in Ihrem Code. Verwenden Sie stattdessen <xref:System.Text.Json.JsonSerializer> oder <xref:System.Xml.Serialization.XmlSerializer>. Weitere Informationen finden Sie im [BinaryFormatter-Sicherheitsleitfaden](../../../../docs/standard/serialization/binaryformatter-security-guide.md).

- Sie können vorübergehend die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Warnung zur Kompilierzeit unterdrücken, die `SYSLIB0011` lautet. Es empfiehlt sich, Ihren Code gründlich auf Risiken zu untersuchen, bevor Sie sich für diese Option entscheiden. Die Warnungen lassen sich am einfachsten unterdrücken, indem Sie die einzelne Aufrufsite mit `#pragma`-Anweisungen umschließen.

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

  Sie können die Warnung auch in der Projektdatei unterdrücken.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  Wenn Sie die Warnung in der Projektdatei unterdrücken, wird sie für alle Codedateien im Projekt unterdrückt. Durch Unterdrücken von SYSLIB0011 werden keine Warnungen unterdrückt, die von anderen veralteten APIs verursacht werden.

- Um <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> weiterhin in ASP.NET-Apps zu verwenden, können Sie die Option in der Projektdatei wieder aktivieren. Es wird jedoch dringend empfohlen, dies nicht zu tun. Weitere Informationen finden Sie im [BinaryFormatter-Sicherheitsleitfaden](../../../../docs/standard/serialization/binaryformatter-security-guide.md).

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

Weitere Informationen zu empfohlenen Aktionen finden Sie unter [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter) (Auflösen von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter).

#### <a name="category"></a>Kategorie

- Core .NET-Bibliotheken
- ASP.NET

#### <a name="affected-apis"></a>Betroffene APIs

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
