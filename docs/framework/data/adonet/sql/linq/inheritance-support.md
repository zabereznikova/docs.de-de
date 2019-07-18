---
title: Unterstützung von Vererbung
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 576fa896364d603f2cdbb7b6532e3efc3cd6f674
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743072"
---
# <a name="inheritance-support"></a>Unterstützung von Vererbung
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt *Zuordnung zu einer einzelnen Tabelle*. In anderen Worten, eine vollständige Vererbungshierarchie wird in einer einzelnen Datenbanktabelle gespeichert. Die Tabelle enthält die vereinfachte Gesamtheit aller möglichen Datenspalten für die gesamte Hierarchie. (Diese Gesamtheit ist das Ergebnis der Kombination von zwei Tabellen in einer Tabelle mit den Zeilen aus den Originaltabellen.) Jede Zeile enthält Nullen in den Spalten, die nicht für den Instanztyp gelten, der von der Spalte dargestellt wird.  
  
 Die Strategie der Zuordnung zu einer einzelnen Tabelle ist die einfachste Darstellung der Vererbung und bietet gute Leistungsmerkmale für viele verschiedene Abfragekategorien.  
  
 Zur Implementierung dieser Zuordnung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] müssen Sie die Attribute in der Stammklasse der Vererbungshierarchie angeben. Weitere Informationen finden Sie unter [Vorgehensweise: Zuordnen von Vererbungshierarchien](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).  
  
 Entwickler, die mithilfe von Visual Studio können auch den Object Relational Designer verwenden, um Vererbungshierarchien zuzuordnen.  
  
## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
