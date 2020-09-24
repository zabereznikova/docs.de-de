---
title: Grundlegende Datentypen
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: ae561bad3315977ba12dd0e12abda1da163ca456
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156016"
---
# <a name="basic-data-types"></a>Grundlegende Datentypen

Da LINQ to SQL-Abfragen vor ihrer Ausführung auf dem Microsoft SQL Server in Transact-SQL übersetzt werden, unterstützt LINQ to SQL einen Großteil der integrierten Funktionen, die SQL Server für grundlegende Datentypen bereitstellt.  
  
## <a name="casting"></a>Umwandlung  

 Implizite und explizite Umwandlungen von einem CLR-Quell- in einen CLR-Zieltyp werden unterstützt, wenn in SQL Server eine ähnliche gültige Konvertierung existiert. Weitere Informationen zur CLR-Umwandlung finden Sie unter [CType-Funktion](../../../../../visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) und [Typtest-und Umwandlungs Operatoren](../../../../../csharp/language-reference/operators/type-testing-and-cast.md). Nach der Konvertierung passen Varianten das Verhalten der durchgeführten Operationen für einen CLR-Ausdruck an das Verhalten anderer CLR-Ausdrücke an, die auf natürliche Weise dem Zieltyp zugewiesen werden. Umwandlungen sind auch im Kontext der Vererbungszuordnung übersetzbar. Objekte können in spezifischere Entitätsuntertypen umgewandelt werden, damit auf ihre untertypspezifischen Daten zugegriffen werden kann.  
  
## <a name="equality-operators"></a>Gleichheitsoperatoren  

 LINQ to SQL unterstützt die folgenden Gleichheitsoperatoren für grundlegende Datentypen in LINQ to SQL-Abfragen:  
  
- Gleichheits-und Ungleichheits Operator: Gleichheits-und Ungleichheits Operatoren werden für numerische <xref:System.Boolean> Typen,, und unterstützt <xref:System.DateTime> <xref:System.TimeSpan> . Weitere Informationen zu Visual Basic-Operatoren `=` und `<>` finden Sie unter [Vergleichs Operatoren](../../../../../visual-basic/language-reference/operators/comparison-operators.md). Weitere Informationen zu c#-Vergleichs Operatoren `==` und `!=` finden Sie unter [Gleichheits Operatoren](../../../../../csharp/language-reference/operators/equality-operators.md).
  
- "Is"-Operator: Der `IS`-Operator verfügt über eine unterstützte Übersetzung, wenn Vererbungsmapping verwendet wird. Er kann anstelle der direkten Prüfung der Diskriminatorspalte verwendet werden, um festzulegen, ob ein Objekt einen bestimmten Typ aufweist. Er wird in eine Prüfung der Diskriminatorspalte übersetzt. Weitere Informationen zu den Visual Basic-und c#-Operatoren finden Sie unter [is-Operator](../../../../../visual-basic/language-reference/operators/is-operator.md) und [ist](../../../../../csharp/language-reference/operators/type-testing-and-cast.md#is-operator).  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL-CLR-Typenzuordnung](sql-clr-type-mapping.md)
- [Datentypen und Funktionen](data-types-and-functions.md)
