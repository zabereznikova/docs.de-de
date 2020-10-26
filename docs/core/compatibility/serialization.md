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
# <a name="serialization-breaking-changes"></a><span data-ttu-id="aa029-103">Breaking Changes bei der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="aa029-103">Serialization breaking changes</span></span>

<span data-ttu-id="aa029-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="aa029-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="aa029-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="aa029-105">Breaking change</span></span> | <span data-ttu-id="aa029-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="aa029-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="aa029-107">Die Optionen „PropertyNamingPolicy“, „PropertyNamingPolicy“ und „Encoder“ werden beim Serialisieren und Deserialisieren von Schlüssel-Wert-Paaren berücksichtigt</span><span class="sxs-lookup"><span data-stu-id="aa029-107">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | <span data-ttu-id="aa029-108">5.0</span><span class="sxs-lookup"><span data-stu-id="aa029-108">5.0</span></span> |
| [<span data-ttu-id="aa029-109">Nicht öffentliche parameterlose Konstruktoren, die nicht für die Deserialisierung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="aa029-109">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="aa029-110">5.0</span><span class="sxs-lookup"><span data-stu-id="aa029-110">5.0</span></span> |
| [<span data-ttu-id="aa029-111">JsonSerializer.Serialize gibt eine ArgumentNullException-Ausnahme zurück, wenn für den Typparameter NULL gilt</span><span class="sxs-lookup"><span data-stu-id="aa029-111">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="aa029-112">5.0</span><span class="sxs-lookup"><span data-stu-id="aa029-112">5.0</span></span> |
| [<span data-ttu-id="aa029-113">JsonSerializer.Deserialize erfordert Zeichenfolgen mit einzelnem Zeichen</span><span class="sxs-lookup"><span data-stu-id="aa029-113">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="aa029-114">5.0</span><span class="sxs-lookup"><span data-stu-id="aa029-114">5.0</span></span> |
| [<span data-ttu-id="aa029-115">BinaryFormatter.Deserialize umschließt einige Ausnahmen in SerializationException erneut</span><span class="sxs-lookup"><span data-stu-id="aa029-115">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="aa029-116">5.0</span><span class="sxs-lookup"><span data-stu-id="aa029-116">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="aa029-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="aa029-117">.NET 5.0</span></span>

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
