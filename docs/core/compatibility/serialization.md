---
title: Breaking Changes bei der Serialisierung
description: Hier werden Breaking Changes bei der Serialisierung in .NET Core und .NET 5.0 und höheren Versionen aufgeführt.
ms.date: 07/30/2020
ms.openlocfilehash: f635ff2cd233922a0bbb327de23c8bf25d344fa0
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517409"
---
# <a name="serialization-breaking-changes"></a>Breaking Changes bei der Serialisierung

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | - |
| [BinaryFormatter.Deserialize umschließt einige Ausnahmen in SerializationException erneut](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5.0 |

## <a name="net-core-50"></a>.NET Core 5.0

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
