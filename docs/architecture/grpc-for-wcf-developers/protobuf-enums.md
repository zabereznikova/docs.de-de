---
title: Protobuf-Enumerationen-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie Enumerationen in protobuf deklarieren und verwenden.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: f18196f54caba824d7101782a88cf3bf699560d5
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841414"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="e74a8-103">Protobuf-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e74a8-103">Protobuf enumerations</span></span>

<span data-ttu-id="e74a8-104">Protobuf unterstützt Enumerationstypen, wie im vorherigen Abschnitt gezeigt, in dem eine Enumeration verwendet wurde, um den Typ eines `oneof` Felds zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e74a8-104">Protobuf supports enumeration types, as seen in the previous section where an enum was used to determine the type of a `oneof` field.</span></span> <span data-ttu-id="e74a8-105">Sie können eigene Enumerationstypen definieren, und protobuf kompiliert Sie C# in Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="e74a8-105">You can define your own enumeration types and Protobuf will compile them to C# enum types.</span></span> <span data-ttu-id="e74a8-106">Da protobuf mit verschiedenen Sprachen verwendet werden kann, unterscheiden sich die Benennungs Konventionen für Enumerationen C# von den Konventionen.</span><span class="sxs-lookup"><span data-stu-id="e74a8-106">Since Protobuf can be used with different languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="e74a8-107">Der Code-Generator ist jedoch clever und konvertiert die Namen in den herkömmlichen C# Fall.</span><span class="sxs-lookup"><span data-stu-id="e74a8-107">However, the code generator is clever and converts the names to the traditional C# case.</span></span> <span data-ttu-id="e74a8-108">Wenn die Pascal-Case-Entsprechung des Feldnamens mit dem Enumerationsnamen beginnt, wird Sie entfernt.</span><span class="sxs-lookup"><span data-stu-id="e74a8-108">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="e74a8-109">In dieser protobuf-Enumeration werden den Feldern z. b. `ACCOUNT_STATUS`vorangestellt, was dem Namen der Pascal-fallenumeration entspricht: `AccountStatus`.</span><span class="sxs-lookup"><span data-stu-id="e74a8-109">For example, in this Protobuf enumeration the fields are prefixed with `ACCOUNT_STATUS`, which is equivalent to the Pascal case enum name: `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="e74a8-110">Daher erstellt der Generator eine C# Aufzählung, die dem folgenden Code entspricht:</span><span class="sxs-lookup"><span data-stu-id="e74a8-110">So, the generator creates a C# enum equivalent to the following code:</span></span>

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

<span data-ttu-id="e74a8-111">Protobuf-Enumerationsdefinitionen **müssen** als erstes Feld eine Konstante von 0 (null) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e74a8-111">Protobuf enumeration definitions **must** have a zero constant as their first field.</span></span> <span data-ttu-id="e74a8-112">Wie in C#können Sie mehrere Felder mit demselben Wert deklarieren. Sie müssen diese Option jedoch explizit mithilfe der Option `allow_alias` in der Enumeration aktivieren:</span><span class="sxs-lookup"><span data-stu-id="e74a8-112">As in C#, you can declare multiple fields with the same value, but you must explicitly enable this option using the `allow_alias` option in the enum:</span></span>

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

<span data-ttu-id="e74a8-113">Sie können Enumerationen auf der obersten Ebene in einer `.proto` Datei deklarieren oder innerhalb einer Nachrichten Definition geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="e74a8-113">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="e74a8-114">Geschachtelte Enumerationen – wie geschachtelte Nachrichten – werden innerhalb der statischen Klasse `.Types` in der generierten Message-Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="e74a8-114">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="e74a8-115">Es gibt keine Möglichkeit, das [[Flags]](xref:System.FlagsAttribute) -Attribut auf eine protobuf-generierte Enumeration anzuwenden, und protobuf versteht keine bitweisen Enumeration-Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="e74a8-115">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="e74a8-116">Sehen Sie sich das folgende Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="e74a8-116">Take a look at the following example:</span></span>

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

<span data-ttu-id="e74a8-117">Wenn Sie `product.AvailableIn` auf `Region.NorthAmerica | Region.SouthAmerica`festlegen, wird es als ganzzahliger Wert `3`serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e74a8-117">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="e74a8-118">Wenn ein Client oder Server versucht, den Wert zu deserialisieren, findet keine Entsprechung in der Enumerationsdefinition für `3`, und das Ergebnis wird `Region.None`.</span><span class="sxs-lookup"><span data-stu-id="e74a8-118">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3` and the result will be `Region.None`.</span></span>

<span data-ttu-id="e74a8-119">Die beste Möglichkeit zum Arbeiten mit mehreren Enumerationswerten in protobuf ist die Verwendung eines `repeated` Felds des Enumerationstyps.</span><span class="sxs-lookup"><span data-stu-id="e74a8-119">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e74a8-120">[Zurück](protobuf-any-oneof.md)
>[Weiter](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="e74a8-120">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
