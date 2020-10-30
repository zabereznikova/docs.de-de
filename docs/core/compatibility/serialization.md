---
title: Breaking Changes bei der Serialisierung
description: Hier werden Breaking Changes bei der Serialisierung in .NET Core und .NET 5.0 und höheren Versionen aufgeführt.
ms.date: 07/30/2020
ms.openlocfilehash: 67608c8e7a9745c060b7eb179fe5a956ede9f80f
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332878"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="4a096-103">Breaking Changes bei der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4a096-103">Serialization breaking changes</span></span>

<span data-ttu-id="4a096-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="4a096-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="4a096-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="4a096-105">Breaking change</span></span> | <span data-ttu-id="4a096-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="4a096-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="4a096-107">ASP.NET Core-Apps erlauben die Deserialisierung von Zahlen in Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="4a096-107">ASP.NET Core apps allow deserializing quoted numbers</span></span>](#aspnet-core-apps-allow-deserializing-quoted-numbers) | <span data-ttu-id="4a096-108">5.0</span><span class="sxs-lookup"><span data-stu-id="4a096-108">5.0</span></span> |
| [<span data-ttu-id="4a096-109">Die Optionen „PropertyNamingPolicy“, „PropertyNamingPolicy“ und „Encoder“ werden beim Serialisieren und Deserialisieren von Schlüssel-Wert-Paaren berücksichtigt</span><span class="sxs-lookup"><span data-stu-id="4a096-109">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | <span data-ttu-id="4a096-110">5.0</span><span class="sxs-lookup"><span data-stu-id="4a096-110">5.0</span></span> |
| [<span data-ttu-id="4a096-111">Nicht öffentliche parameterlose Konstruktoren, die nicht für die Deserialisierung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="4a096-111">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="4a096-112">5.0</span><span class="sxs-lookup"><span data-stu-id="4a096-112">5.0</span></span> |
| [<span data-ttu-id="4a096-113">JsonSerializer.Serialize gibt eine ArgumentNullException-Ausnahme zurück, wenn für den Typparameter NULL gilt</span><span class="sxs-lookup"><span data-stu-id="4a096-113">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="4a096-114">5.0</span><span class="sxs-lookup"><span data-stu-id="4a096-114">5.0</span></span> |
| [<span data-ttu-id="4a096-115">JsonSerializer.Deserialize erfordert Zeichenfolgen mit einzelnem Zeichen</span><span class="sxs-lookup"><span data-stu-id="4a096-115">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="4a096-116">5.0</span><span class="sxs-lookup"><span data-stu-id="4a096-116">5.0</span></span> |
| [<span data-ttu-id="4a096-117">BinaryFormatter.Deserialize umschließt einige Ausnahmen in SerializationException erneut</span><span class="sxs-lookup"><span data-stu-id="4a096-117">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="4a096-118">5.0</span><span class="sxs-lookup"><span data-stu-id="4a096-118">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="4a096-119">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="4a096-119">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-allows-reading-numbers-as-strings](../../../includes/core-changes/serialization/5.0/jsonserializer-allows-reading-numbers-as-strings.md)]

***

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

<span data-ttu-id="4a096-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="4a096-120">\*\*_</span></span>

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

_*_

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

_*_

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

_*_

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

<span data-ttu-id="4a096-121">_\*\*</span><span class="sxs-lookup"><span data-stu-id="4a096-121">_\*\*</span></span>
