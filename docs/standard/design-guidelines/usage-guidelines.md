---
title: Verwendungsrichtlinien
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: d6ea7c7b9ada95e3d0c425aaea18be6cdbb4ce35
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828503"
---
# <a name="usage-guidelines"></a><span data-ttu-id="d8b64-102">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d8b64-102">Usage guidelines</span></span>

<span data-ttu-id="d8b64-103">Dieser Abschnitt enthält Richtlinien für die Verwendung gängiger Typen in öffentlich zugänglichen APIs.</span><span class="sxs-lookup"><span data-stu-id="d8b64-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="d8b64-104">Es behandelt die direkte Verwendung integrierter Frameworktypen (z. b. Serialisierungsattribute) und das überladen allgemeiner Operatoren.</span><span class="sxs-lookup"><span data-stu-id="d8b64-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="d8b64-105">Die- <xref:System.IDisposable?displayProperty=nameWithType> Schnittstelle wird in diesem Abschnitt nicht behandelt, wird jedoch im Abschnitt Verwerfen von [Mustern](../garbage-collection/implementing-dispose.md) erläutert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="d8b64-106">Richtlinien und zusätzliche Informationen über andere gängige, integrierte .NET Framework Typen finden Sie in den Referenz Themen zu den folgenden Themen: <xref:System.DateTime?displayProperty=nameWithType> , <xref:System.DateTimeOffset?displayProperty=nameWithType> , <xref:System.ICloneable?displayProperty=nameWithType> , <xref:System.IComparable%601?displayProperty=nameWithType> , <xref:System.IEquatable%601?displayProperty=nameWithType> , <xref:System.Nullable%601?displayProperty=nameWithType> , <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d8b64-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d8b64-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d8b64-107">In this section</span></span>

[<span data-ttu-id="d8b64-108">Arrays</span><span class="sxs-lookup"><span data-stu-id="d8b64-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="d8b64-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d8b64-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="d8b64-110">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="d8b64-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="d8b64-111">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d8b64-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="d8b64-112">System.Xml Verwendung</span><span class="sxs-lookup"><span data-stu-id="d8b64-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="d8b64-113">Gleichheits Operatoren</span><span class="sxs-lookup"><span data-stu-id="d8b64-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="d8b64-114">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="d8b64-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="d8b64-115">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d8b64-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d8b64-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8b64-116">See also</span></span>

- [<span data-ttu-id="d8b64-117">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d8b64-117">Framework Design Guidelines</span></span>](index.md)
