---
title: Verwendungsrichtlinien
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: KrzysztofCwalina
ms.openlocfilehash: 23b1520a864d41e5ef59377cc9cca34cbdf22b64
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423048"
---
# <a name="usage-guidelines"></a><span data-ttu-id="d257f-102">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d257f-102">Usage guidelines</span></span>

<span data-ttu-id="d257f-103">Dieser Abschnitt enthält Richtlinien für die Verwendung gängiger Typen in öffentlich zugänglichen APIs.</span><span class="sxs-lookup"><span data-stu-id="d257f-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="d257f-104">Es behandelt die direkte Verwendung integrierter Frameworktypen (z. b. Serialisierungsattribute) und das überladen allgemeiner Operatoren.</span><span class="sxs-lookup"><span data-stu-id="d257f-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="d257f-105">Die <xref:System.IDisposable?displayProperty=nameWithType>-Schnittstelle wird in diesem Abschnitt nicht behandelt, wird jedoch im Abschnitt Verwerfen von [Mustern](../garbage-collection/implementing-dispose.md) erläutert.</span><span class="sxs-lookup"><span data-stu-id="d257f-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="d257f-106">Richtlinien und zusätzliche Informationen über andere gängige, integrierte .NET Framework Typen finden Sie in den Referenz Themen zu den folgenden Themen: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d257f-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d257f-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d257f-107">In this section</span></span>

[<span data-ttu-id="d257f-108">Arrays</span><span class="sxs-lookup"><span data-stu-id="d257f-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="d257f-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d257f-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="d257f-110">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="d257f-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="d257f-111">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d257f-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="d257f-112">Verwendung von System.Xml</span><span class="sxs-lookup"><span data-stu-id="d257f-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="d257f-113">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="d257f-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="d257f-114">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="d257f-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="d257f-115">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d257f-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d257f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d257f-116">See also</span></span>

- [<span data-ttu-id="d257f-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d257f-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
