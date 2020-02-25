---
title: Protobuf-Enumerationen-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie Enumerationen in protobuf deklarieren und verwenden.
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543143"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="0bf4e-103">Protobuf-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0bf4e-103">Protobuf enumerations</span></span>

<span data-ttu-id="0bf4e-104">Protobuf unterstützt Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="0bf4e-105">Diese Unterstützung wurde im vorherigen Abschnitt erläutert, in dem eine-Auflistung verwendet wurde, um den Typ eines `Oneof` Felds zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="0bf4e-106">Sie können eigene Enumerationstypen definieren, und protobuf kompiliert Sie in C# Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span> 

<span data-ttu-id="0bf4e-107">Da Sie protobuf mit verschiedenen Sprachen verwenden können, unterscheiden sich die Benennungs Konventionen für Enumerationen C# von den Konventionen.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="0bf4e-108">Der Code-Generator konvertiert die Namen jedoch in den herkömmlichen C# Fall.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="0bf4e-109">Wenn die Pascal-Case-Entsprechung des Feldnamens mit dem Enumerationsnamen beginnt, wird Sie entfernt.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="0bf4e-110">In der folgenden protobuf-Enumeration werden den Feldern z. b. `ACCOUNT_STATUS`vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="0bf4e-111">Dieses Präfix entspricht dem Namen der "Pascal-Case-Enumeration", "`AccountStatus`".</span><span class="sxs-lookup"><span data-stu-id="0bf4e-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="0bf4e-112">Der Generator erstellt eine C# Aufzählung, die dem folgenden Code entspricht:</span><span class="sxs-lookup"><span data-stu-id="0bf4e-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="0bf4e-113">Protobuf-Enumerationsdefinitionen *müssen* als erstes Feld eine Konstante von 0 (null) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="0bf4e-114">Wie in C#können Sie mehrere Felder mit dem gleichen Wert deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="0bf4e-115">Sie müssen diese Option jedoch explizit aktivieren, indem Sie die Option `allow_alias` in der-Aufzählung verwenden:</span><span class="sxs-lookup"><span data-stu-id="0bf4e-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="0bf4e-116">Sie können Enumerationen auf der obersten Ebene in einer `.proto` Datei deklarieren oder innerhalb einer Nachrichten Definition geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="0bf4e-117">Geschachtelte Enumerationen – wie geschachtelte Nachrichten – werden innerhalb der statischen Klasse `.Types` in der generierten Message-Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="0bf4e-118">Es gibt keine Möglichkeit, das [[Flags]](xref:System.FlagsAttribute) -Attribut auf eine protobuf-generierte Enumeration anzuwenden, und protobuf versteht keine bitweisen Enumeration-Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="0bf4e-119">Sehen Sie sich das folgende Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="0bf4e-119">Look at the following example:</span></span>

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

<span data-ttu-id="0bf4e-120">Wenn Sie `product.AvailableIn` auf `Region.NorthAmerica | Region.SouthAmerica`festlegen, wird es als ganzzahliger Wert `3`serialisiert.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="0bf4e-121">Wenn ein Client oder Server versucht, den Wert zu deserialisieren, findet keine Entsprechung in der Enumerationsdefinition für `3`.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="0bf4e-122">Das Ergebnis wird `Region.None`.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="0bf4e-123">Die beste Möglichkeit zum Arbeiten mit mehreren Enumerationswerten in protobuf ist die Verwendung eines `repeated` Felds des Enumerationstyps.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0bf4e-124">[Zurück](protobuf-any-oneof.md)
>[Weiter](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="0bf4e-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
