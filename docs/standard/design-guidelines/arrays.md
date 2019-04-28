---
title: Arrays
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: KrzysztofCwalina
ms.openlocfilehash: dd30cdee0440553a9f955f0b3f4ee420e938b9ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864116"
---
# <a name="arrays"></a><span data-ttu-id="28195-102">Arrays</span><span class="sxs-lookup"><span data-stu-id="28195-102">Arrays</span></span>
<span data-ttu-id="28195-103">**✓ DO** lieber mithilfe von Sammlungen über Arrays in öffentlichen APIs.</span><span class="sxs-lookup"><span data-stu-id="28195-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="28195-104">Die [Sammlungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) Abschnitt enthält ausführliche Informationen zur Wahl zwischen Auflistungen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="28195-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="28195-105">**X DO NOT** schreibgeschützte Arrayfelder verwenden.</span><span class="sxs-lookup"><span data-stu-id="28195-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="28195-106">Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber der Elemente im Array können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="28195-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="28195-107">**✓ CONSIDER** verzweigte Arrays anstelle von mehrdimensionalen Arrays verwenden.</span><span class="sxs-lookup"><span data-stu-id="28195-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="28195-108">Ein verzweigtes Array ist ein Array mit Elementen, die auch Arrays sind.</span><span class="sxs-lookup"><span data-stu-id="28195-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="28195-109">Die Arrays, die die Elemente bilden können unterschiedliche Größen haben, führt zu weniger Speicherplatz vergeudet bei einigen Gruppen von Daten (z. B. mit geringer Dichte Matrix) im Vergleich zu mehrdimensionalen Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="28195-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="28195-110">Darüber hinaus wird die CLR Indexvorgänge auf verzweigte Arrays optimiert, damit sie möglicherweise eine bessere Leistung zur Laufzeit in einigen Szenarien weisen.</span><span class="sxs-lookup"><span data-stu-id="28195-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="28195-111">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="28195-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="28195-112">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="28195-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28195-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28195-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="28195-114">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="28195-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="28195-115">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="28195-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
