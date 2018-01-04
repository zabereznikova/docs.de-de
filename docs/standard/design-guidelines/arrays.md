---
title: Arrays
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2e634cdcff0b1b2968a3b64d8d05cb57feeddb51
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="arrays"></a><span data-ttu-id="d161c-102">Arrays</span><span class="sxs-lookup"><span data-stu-id="d161c-102">Arrays</span></span>
<span data-ttu-id="d161c-103">**Führen Sie ✓** lieber mithilfe von Sammlungen über Arrays in öffentlichen APIs.</span><span class="sxs-lookup"><span data-stu-id="d161c-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="d161c-104">Die [Sammlungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) Abschnitt bietet ausführliche Informationen zur Wahl zwischen Auflistungen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="d161c-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="d161c-105">**X nicht** schreibgeschützte Arrayfelder verwenden.</span><span class="sxs-lookup"><span data-stu-id="d161c-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="d161c-106">Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber Elemente im Array können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d161c-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="d161c-107">**✓ GGF.** verzweigte Arrays anstelle von mehrdimensionalen Arrays verwenden.</span><span class="sxs-lookup"><span data-stu-id="d161c-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="d161c-108">Ein verzweigtes Array ist ein Array mit Elementen, die auch Arrays sind.</span><span class="sxs-lookup"><span data-stu-id="d161c-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="d161c-109">Die Arrays, die die Elemente bilden können unterschiedliche Größen haben, was zu weniger Speicherplatz vergeudet bei einigen Gruppen von Daten (z. B. mit geringer Dichte Matrix) im Vergleich zu mehrdimensionalen Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="d161c-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="d161c-110">Darüber hinaus optimiert die CLR Indexvorgänge auf verzweigte Arrays, damit sie eine bessere Leistung zur Laufzeit in einigen Szenarien weisen möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="d161c-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="d161c-111">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="d161c-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d161c-112">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="d161c-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d161c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d161c-113">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="d161c-114">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d161c-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="d161c-115">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d161c-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
