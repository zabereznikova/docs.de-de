---
title: Nutzungsrichtlinien
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bd54a2325c9721ad17943ba663e7ec0c300632e
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925075"
---
# <a name="usage-guidelines"></a><span data-ttu-id="ff0b3-102">Nutzungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ff0b3-102">Usage guidelines</span></span>

<span data-ttu-id="ff0b3-103">Dieser Abschnitt enthält Richtlinien für die Verwendung von häufig verwendeten Typen in öffentlich zugängliche-APIs.</span><span class="sxs-lookup"><span data-stu-id="ff0b3-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="ff0b3-104">Er behandelt die direkte Verwendung von integrierten Framework-Typen (z. B. Serialisierungsattribute) und allgemeine Operatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="ff0b3-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="ff0b3-105">Die <xref:System.IDisposable?displayProperty=nameWithType> Schnittstelle wird in diesem Abschnitt nicht behandelt, aber es wird erläutert, der [Dispose-Muster](../../../docs/standard/design-guidelines/dispose-pattern.md) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ff0b3-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="ff0b3-106">Richtlinien und zusätzliche Informationen über andere gängige, integrierte .NET Framework-Typen finden Sie unter den Referenzthemen für die folgenden: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ff0b3-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ff0b3-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ff0b3-107">In this section</span></span>

[<span data-ttu-id="ff0b3-108">Arrays</span><span class="sxs-lookup"><span data-stu-id="ff0b3-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="ff0b3-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="ff0b3-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="ff0b3-110">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="ff0b3-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="ff0b3-111">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="ff0b3-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="ff0b3-112">Verwendung von System.Xml</span><span class="sxs-lookup"><span data-stu-id="ff0b3-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="ff0b3-113">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="ff0b3-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="ff0b3-114">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ff0b3-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="ff0b3-115">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ff0b3-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff0b3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff0b3-116">See also</span></span>

[<span data-ttu-id="ff0b3-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ff0b3-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
