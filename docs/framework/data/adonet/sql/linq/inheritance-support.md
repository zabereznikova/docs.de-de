---
title: Unterstützung von Vererbung
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 7673e69458d5c1af854747c43ba463332a9cd588
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158252"
---
# <a name="inheritance-support"></a><span data-ttu-id="fd2a1-102">Unterstützung von Vererbung</span><span class="sxs-lookup"><span data-stu-id="fd2a1-102">Inheritance Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fd2a1-103">unterstützt die *Zuordnung einer einzelnen Tabelle*.</span><span class="sxs-lookup"><span data-stu-id="fd2a1-103">supports *single-table mapping*.</span></span> <span data-ttu-id="fd2a1-104">In anderen Worten, eine vollständige Vererbungshierarchie wird in einer einzelnen Datenbanktabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fd2a1-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="fd2a1-105">Die Tabelle enthält die vereinfachte Gesamtheit aller möglichen Datenspalten für die gesamte Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="fd2a1-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="fd2a1-106">(Eine Union ist das Ergebnis der Kombination zweier Tabellen in einer Tabelle, die die Zeilen enthält, die in einer der ursprünglichen Tabellen vorhanden waren.) Jede Zeile enthält NULL-Werten in den Spalten, die nicht für den Typ der Instanz gelten, die durch die Zeile dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fd2a1-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="fd2a1-107">Die Strategie der Zuordnung zu einer einzelnen Tabelle ist die einfachste Darstellung der Vererbung und bietet gute Leistungsmerkmale für viele verschiedene Abfragekategorien.</span><span class="sxs-lookup"><span data-stu-id="fd2a1-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="fd2a1-108">Zur Implementierung dieser Zuordnung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] müssen Sie die Attribute in der Stammklasse der Vererbungshierarchie angeben.</span><span class="sxs-lookup"><span data-stu-id="fd2a1-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="fd2a1-109">Weitere Informationen finden Sie unter Vorgehens [Weise: Zuordnen von Vererbungs Hierarchien](how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="fd2a1-109">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="fd2a1-110">Entwickler, die Visual Studio verwenden, können auch den objektrelationaler Designer verwenden, um Vererbungs Hierarchien zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fd2a1-110">Developers using Visual Studio can also use the Object Relational Designer to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2a1-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd2a1-111">See also</span></span>

- [<span data-ttu-id="fd2a1-112">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="fd2a1-112">Background Information</span></span>](background-information.md)
