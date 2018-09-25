---
title: Arrays
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080952"
---
# <a name="arrays"></a><span data-ttu-id="009dc-102">Arrays</span><span class="sxs-lookup"><span data-stu-id="009dc-102">Arrays</span></span>
<span data-ttu-id="009dc-103">**✓ DO** lieber mithilfe von Sammlungen über Arrays in öffentlichen APIs.</span><span class="sxs-lookup"><span data-stu-id="009dc-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="009dc-104">Die [Sammlungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) Abschnitt enthält ausführliche Informationen zur Wahl zwischen Auflistungen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="009dc-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="009dc-105">**X DO NOT** schreibgeschützte Arrayfelder verwenden.</span><span class="sxs-lookup"><span data-stu-id="009dc-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="009dc-106">Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber der Elemente im Array können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="009dc-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="009dc-107">**✓ CONSIDER** verzweigte Arrays anstelle von mehrdimensionalen Arrays verwenden.</span><span class="sxs-lookup"><span data-stu-id="009dc-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="009dc-108">Ein verzweigtes Array ist ein Array mit Elementen, die auch Arrays sind.</span><span class="sxs-lookup"><span data-stu-id="009dc-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="009dc-109">Die Arrays, die die Elemente bilden können unterschiedliche Größen haben, führt zu weniger Speicherplatz vergeudet bei einigen Gruppen von Daten (z. B. mit geringer Dichte Matrix) im Vergleich zu mehrdimensionalen Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="009dc-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="009dc-110">Darüber hinaus wird die CLR Indexvorgänge auf verzweigte Arrays optimiert, damit sie möglicherweise eine bessere Leistung zur Laufzeit in einigen Szenarien weisen.</span><span class="sxs-lookup"><span data-stu-id="009dc-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="009dc-111">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="009dc-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="009dc-112">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="009dc-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009dc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="009dc-113">See also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="009dc-114">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="009dc-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="009dc-115">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="009dc-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
