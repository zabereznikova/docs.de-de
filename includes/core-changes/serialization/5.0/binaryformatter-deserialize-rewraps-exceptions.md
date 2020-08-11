---
ms.openlocfilehash: 2e9267b35c9389da017927aca2346190348265c9
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87919305"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a>BinaryFormatter.Deserialize umschließt einige Ausnahmen in SerializationException erneut

Die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode umschließt jetzt einige Ausnahmeobjekte innerhalb einer <xref:System.Runtime.Serialization.SerializationException> erneut, bevor die Ausnahme an den Aufrufer zurückgegeben wird.

#### <a name="change-description"></a>Änderungsbeschreibung

Bisher erlaubte die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode die Weitergabe einiger zufälliger Ausnahmen, wie z. B. <xref:System.ArgumentNullException> den Stapel entlang zu den Aufrufern.

In .NET 5.0 und höher fängt die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode Ausnahmen aufgrund von ungültigen Deserialisierungsvorgängen aggressiver ab und umschließt sie in einer <xref:System.Runtime.Serialization.SerializationException>.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 1

#### <a name="recommended-action"></a>Empfohlene Aktion

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

#### <a name="category"></a>Kategorie

Serialisierung

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->
