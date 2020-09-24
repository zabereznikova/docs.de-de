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
# <a name="inheritance-support"></a>Unterstützung von Vererbung

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die *Zuordnung einer einzelnen Tabelle*. In anderen Worten, eine vollständige Vererbungshierarchie wird in einer einzelnen Datenbanktabelle gespeichert. Die Tabelle enthält die vereinfachte Gesamtheit aller möglichen Datenspalten für die gesamte Hierarchie. (Eine Union ist das Ergebnis der Kombination zweier Tabellen in einer Tabelle, die die Zeilen enthält, die in einer der ursprünglichen Tabellen vorhanden waren.) Jede Zeile enthält NULL-Werten in den Spalten, die nicht für den Typ der Instanz gelten, die durch die Zeile dargestellt wird.  
  
 Die Strategie der Zuordnung zu einer einzelnen Tabelle ist die einfachste Darstellung der Vererbung und bietet gute Leistungsmerkmale für viele verschiedene Abfragekategorien.  
  
 Zur Implementierung dieser Zuordnung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] müssen Sie die Attribute in der Stammklasse der Vererbungshierarchie angeben. Weitere Informationen finden Sie unter Vorgehens [Weise: Zuordnen von Vererbungs Hierarchien](how-to-map-inheritance-hierarchies.md).  
  
 Entwickler, die Visual Studio verwenden, können auch den objektrelationaler Designer verwenden, um Vererbungs Hierarchien zuzuordnen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Hintergrundinformationen](background-information.md)
