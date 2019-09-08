---
title: Unterstützung von Vererbung
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 034aa6e75ca304d98aa4d3e1f3023c1a6940b73c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781570"
---
# <a name="inheritance-support"></a><span data-ttu-id="74fd9-102">Unterstützung von Vererbung</span><span class="sxs-lookup"><span data-stu-id="74fd9-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="74fd9-103">unterstützt die *Zuordnung einer einzelnen Tabelle*.</span><span class="sxs-lookup"><span data-stu-id="74fd9-103">supports *single-table mapping*.</span></span> <span data-ttu-id="74fd9-104">In anderen Worten, eine vollständige Vererbungshierarchie wird in einer einzelnen Datenbanktabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="74fd9-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="74fd9-105">Die Tabelle enthält die vereinfachte Gesamtheit aller möglichen Datenspalten für die gesamte Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="74fd9-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="74fd9-106">(Diese Gesamtheit ist das Ergebnis der Kombination von zwei Tabellen in einer Tabelle mit den Zeilen aus den Originaltabellen.) Jede Zeile enthält Nullen in den Spalten, die nicht für den Instanztyp gelten, der von der Spalte dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="74fd9-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="74fd9-107">Die Strategie der Zuordnung zu einer einzelnen Tabelle ist die einfachste Darstellung der Vererbung und bietet gute Leistungsmerkmale für viele verschiedene Abfragekategorien.</span><span class="sxs-lookup"><span data-stu-id="74fd9-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="74fd9-108">Zur Implementierung dieser Zuordnung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] müssen Sie die Attribute in der Stammklasse der Vererbungshierarchie angeben.</span><span class="sxs-lookup"><span data-stu-id="74fd9-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="74fd9-109">Weitere Informationen finden Sie unter [Vorgehensweise: Zuordnen von Vererbungs Hierarchien](how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="74fd9-109">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="74fd9-110">Entwickler, die Visual Studio verwenden, können auch den objektrelationaler Designer verwenden, um Vererbungs Hierarchien zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="74fd9-110">Developers using Visual Studio can also use the Object Relational Designer to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74fd9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74fd9-111">See also</span></span>

- [<span data-ttu-id="74fd9-112">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="74fd9-112">Background Information</span></span>](background-information.md)
