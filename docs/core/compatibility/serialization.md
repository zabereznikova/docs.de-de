---
title: Breaking Changes bei der Serialisierung
description: Hier werden Breaking Changes bei der Serialisierung in .NET Core und .NET 5.0 und höheren Versionen aufgeführt.
ms.date: 07/30/2020
ms.openlocfilehash: bb6bd650afeba426edc6e102076f05f97f8e0598
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050465"
---
# <a name="serialization-breaking-changes"></a>Breaking Changes bei der Serialisierung

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | - |
| [Die Optionen „PropertyNamingPolicy“, „PropertyNamingPolicy“ und „Encoder“ werden beim Serialisieren und Deserialisieren von Schlüssel-Wert-Paaren berücksichtigt](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | 5.0 |
| [Nicht öffentliche parameterlose Konstruktoren, die nicht für die Deserialisierung verwendet werden](#non-public-parameterless-constructors-not-used-for-deserialization) | 5.0 |
| [JsonSerializer.Serialize gibt eine ArgumentNullException-Ausnahme zurück, wenn für den Typparameter NULL gilt](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | 5.0 |
| [JsonSerializer.Deserialize erfordert Zeichenfolgen mit einzelnem Zeichen](#jsonserializerdeserialize-requires-single-character-string) | 5.0 |
| [BinaryFormatter.Deserialize umschließt einige Ausnahmen in SerializationException erneut](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

***

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

***

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
