---
title: Arrays
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: ac4b073d2d3291922498a0e56c7e81f7e7868c65
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709568"
---
# <a name="arrays"></a><span data-ttu-id="fd4be-102">Arrays</span><span class="sxs-lookup"><span data-stu-id="fd4be-102">Arrays</span></span>
<span data-ttu-id="fd4be-103">**✓ DO** lieber mithilfe von Sammlungen über Arrays in öffentlichen APIs.</span><span class="sxs-lookup"><span data-stu-id="fd4be-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="fd4be-104">Der Abschnitt " [Sammlungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) " enthält Details zur Auswahl zwischen Sammlungen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="fd4be-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="fd4be-105">**X DO NOT** schreibgeschützte Arrayfelder verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd4be-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="fd4be-106">Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber Elemente im Array können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fd4be-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="fd4be-107">**✓ CONSIDER** verzweigte Arrays anstelle von mehrdimensionalen Arrays verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd4be-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="fd4be-108">Ein Jagged Array ist ein Array mit Elementen, die auch Arrays sind.</span><span class="sxs-lookup"><span data-stu-id="fd4be-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="fd4be-109">Die Arrays, aus denen die Elemente bestehen, können unterschiedlich groß sein, was zu weniger vergeudetem Speicherplatz für einige Datensätze (z. b. sparsespalten) im Vergleich zu mehrdimensionalen Arrays führt.</span><span class="sxs-lookup"><span data-stu-id="fd4be-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="fd4be-110">Außerdem optimiert die CLR Index Vorgänge für verzweigte Arrays, sodass Sie in einigen Szenarios möglicherweise eine bessere Laufzeitleistung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fd4be-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="fd4be-111">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="fd4be-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="fd4be-112">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="fd4be-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4be-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd4be-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="fd4be-114">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="fd4be-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="fd4be-115">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="fd4be-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
