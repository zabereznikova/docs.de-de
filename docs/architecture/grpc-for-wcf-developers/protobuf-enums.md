---
title: Protobuf-Enumerationen - gRPC für WCF-Entwickler
description: Erfahren Sie, wie Sie Enumerationen in Protobuf deklarieren und verwenden.
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148074"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="ba3cf-103">Protobuf-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ba3cf-103">Protobuf enumerations</span></span>

<span data-ttu-id="ba3cf-104">Protobuf unterstützt Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="ba3cf-105">Diese Unterstützung wurde im vorherigen Abschnitt angezeigt, in dem eine `Oneof` Enumerat verwendet wurde, um den Typ eines Felds zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="ba3cf-106">Sie können eigene Enumerationstypen definieren, und Protobuf kompiliert sie in C-Enum-Typen.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span>

<span data-ttu-id="ba3cf-107">Da Sie Protobuf in verschiedenen Sprachen verwenden können, unterscheiden sich die Namenskonventionen für Enumerationen von den C-Konventionen.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="ba3cf-108">Der Codegenerator konvertiert jedoch die Namen in den traditionellen C-Fall.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="ba3cf-109">Wenn das Pascal-Case-Äquivalent des Feldnamens mit dem Enumerationsnamen beginnt, wird es entfernt.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="ba3cf-110">In der folgenden Protobuf-Enumeration werden den Feldern `ACCOUNT_STATUS`beispielsweise vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="ba3cf-111">Dieses Präfix entspricht dem Pascal-case-Enumnamen . `AccountStatus`</span><span class="sxs-lookup"><span data-stu-id="ba3cf-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="ba3cf-112">Der Generator erstellt eine C-Enumere, die dem folgenden Code entspricht:</span><span class="sxs-lookup"><span data-stu-id="ba3cf-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="ba3cf-113">Protobuf-Enumerationsdefinitionen *müssen* als erstes Feld eine Nullkonstante haben.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="ba3cf-114">Wie in C- können Sie mehrere Felder mit demselben Wert deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="ba3cf-115">Sie müssen diese Option jedoch `allow_alias` explizit aktivieren, indem Sie die Option in der Enumerat verwenden:</span><span class="sxs-lookup"><span data-stu-id="ba3cf-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="ba3cf-116">Sie können Enumerationen auf der `.proto` obersten Ebene in einer Datei oder in einer Nachrichtendefinition verschachtelt deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="ba3cf-117">Verschachtelte Enumerationen werden – wie geschachtelte Nachrichten – innerhalb der `.Types` statischen Klasse in der generierten Nachrichtenklasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="ba3cf-118">Es gibt keine Möglichkeit, das [[Flags]-Attribut](xref:System.FlagsAttribute) auf eine protobuf-generierte Enumerat anzuwenden, und Protobuf versteht bitweise Enumeronkombinationen nicht.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="ba3cf-119">Sehen Sie sich das folgende Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="ba3cf-119">Look at the following example:</span></span>

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

<span data-ttu-id="ba3cf-120">Wenn Sie `product.AvailableIn` `Region.NorthAmerica | Region.SouthAmerica`auf festlegen, wird er als Ganzzahlwert `3`serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="ba3cf-121">Wenn ein Client oder Server versucht, den Wert zu deserialisieren, findet `3`er keine Übereinstimmung in der Enumeratdefinition für .</span><span class="sxs-lookup"><span data-stu-id="ba3cf-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="ba3cf-122">Das Ergebnis `Region.None`ist .</span><span class="sxs-lookup"><span data-stu-id="ba3cf-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="ba3cf-123">Die beste Möglichkeit, mit mehreren Enumerumwerten in `repeated` Protobuf zu arbeiten, besteht darin, ein Feld des Enumerumtyps zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba3cf-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ba3cf-124">[VorherigeS](protobuf-any-oneof.md)
>[Weiter](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="ba3cf-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
