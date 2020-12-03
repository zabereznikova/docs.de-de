---
title: 'Breaking Change: BinaryFormatter.Deserialize umschließt einige Ausnahmen erneut'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den BinaryFormatter.Deserialize einige Ausnahmeobjekte erneut mit SerializationException umschließt.
ms.date: 08/18/2020
ms.openlocfilehash: 90dc4cce6785fdb38644cca2a2e9aff65eb7a313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759381"
---
# <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a>BinaryFormatter.Deserialize umschließt einige Ausnahmen in SerializationException erneut

Die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode umschließt jetzt einige Ausnahmeobjekte innerhalb einer <xref:System.Runtime.Serialization.SerializationException> erneut, bevor die Ausnahme an den Aufrufer zurückgegeben wird.

## <a name="change-description"></a>Änderungsbeschreibung

Bisher erlaubte die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode die Weitergabe einiger zufälliger Ausnahmen, wie z. B. <xref:System.ArgumentNullException> den Stapel entlang zu den Aufrufern.

In .NET 5.0 und höher fängt die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode Ausnahmen aufgrund von ungültigen Deserialisierungsvorgängen aggressiver ab und umschließt sie in einer <xref:System.Runtime.Serialization.SerializationException>.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

In denen meisten Fällen müssen Sie keine Maßnahmen ergreifen. Wenn es für Ihre Aufrufsite jedoch erforderlich ist, dass eine bestimmte Ausnahme ausgelöst wird, können Sie die Umschließung der Ausnahme in der äußeren <xref:System.Runtime.Serialization.SerializationException> aufheben, wie im folgenden Beispiel gezeigt.

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

### Category

Serialization

-->
