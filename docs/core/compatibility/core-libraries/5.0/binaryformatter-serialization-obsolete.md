---
title: 'Breaking Change: BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die Serialisierungs- und Deserialisierungsmethoden für BinaryFormatter, Formatter und IFormatter als veraltet gelten.
ms.date: 11/01/2020
ms.openlocfilehash: 1dca30d33f2aa0a6fe8f05fe728557092f836b2d
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189843"
---
# <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a>BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten

Die Methoden `Serialize` und `Deserialize` für <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> und <xref:System.Runtime.Serialization.IFormatter> sind nun veraltet und generieren eine Warnung. Darüber hinaus ist die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Serialisierung in ASP.NET-Apps standardmäßig verboten.

## <a name="change-description"></a>Änderungsbeschreibung

Aufgrund von [Sicherheitsrisiken](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> sind die folgenden Methoden jetzt veraltet und lösen zur Kompilierzeit eine Warnung mit der ID `SYSLIB0011` aus. Darüber hinaus wird <xref:System.NotSupportedException> in ASP.NET Core 5.0-Apps (und höher)ausgelöst, es sei denn, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> wurde durch die Web-App wieder aktiviert.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

Die folgenden Serialisierungsmethoden sind jetzt ebenfalls veraltet und lösen die Warnung `SYSLIB0011` aus, führen jedoch nicht zu Änderungen im Verhalten:

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Methoden wurden im Rahmen unsere Bemühungen als veraltet markiert, die Nutzung von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> im .NET-Ökosystem einzudämmen.

## <a name="recommended-action"></a>Empfohlene Aktion

- Verwenden Sie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> nicht mehr in Ihrem Code. Verwenden Sie stattdessen <xref:System.Text.Json.JsonSerializer> oder <xref:System.Xml.Serialization.XmlSerializer>. Weitere Informationen finden Sie im [BinaryFormatter-Sicherheitsleitfaden](../../../../standard/serialization/binaryformatter-security-guide.md).

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

  Wenn Sie die Warnung in der Projektdatei unterdrücken, wird sie für alle Codedateien im Projekt unterdrückt. Durch Unterdrücken von `SYSLIB0011` werden keine Warnungen unterdrückt, die von anderen veralteten APIs verursacht werden.

- Um <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> weiterhin in ASP.NET-Apps zu verwenden, können Sie die Option in der Projektdatei wieder aktivieren. Es wird jedoch dringend empfohlen, dies nicht zu tun. Weitere Informationen finden Sie im [BinaryFormatter-Sicherheitsleitfaden](../../../../standard/serialization/binaryformatter-security-guide.md).

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

Weitere Informationen zu empfohlenen Aktionen finden Sie unter [Resolving BinaryFormatter obsoletion and disablement errors](../../../../standard/serialization/binaryformatter-security-guide.md) (Auflösen von Fehlern aufgrund der Veraltung und Deaktivierung von BinaryFormatter).

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET Core

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
