---
title: Breaking Changes bei der Serialisierung
description: Hier werden Breaking Changes bei der Serialisierung in .NET Core und .NET 5.0 und höheren Versionen aufgeführt.
ms.date: 07/30/2020
ms.openlocfilehash: 65006e6fb45ed2d54699c9972e0489e3ac5ac8bc
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955334"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="3c026-103">Breaking Changes bei der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="3c026-103">Serialization breaking changes</span></span>

<span data-ttu-id="3c026-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="3c026-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="3c026-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="3c026-105">Breaking change</span></span> | <span data-ttu-id="3c026-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3c026-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="3c026-107">JsonSerializer.Serialize gibt eine ArgumentNullException-Ausnahme zurück, wenn für den Typparameter NULL gilt</span><span class="sxs-lookup"><span data-stu-id="3c026-107">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="3c026-108">5.0</span><span class="sxs-lookup"><span data-stu-id="3c026-108">5.0</span></span> |
| [<span data-ttu-id="3c026-109">JsonSerializer.Deserialize erfordert Zeichenfolgen mit einzelnem Zeichen</span><span class="sxs-lookup"><span data-stu-id="3c026-109">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="3c026-110">5.0</span><span class="sxs-lookup"><span data-stu-id="3c026-110">5.0</span></span> |
| [<span data-ttu-id="3c026-111">BinaryFormatter.Deserialize umschließt einige Ausnahmen in SerializationException erneut</span><span class="sxs-lookup"><span data-stu-id="3c026-111">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="3c026-112">5.0</span><span class="sxs-lookup"><span data-stu-id="3c026-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="3c026-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="3c026-113">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
