---
title: Grundlegende Datentypen
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: d9c79ae70d860c5e86d4338038b3158ebfba184f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704968"
---
# <a name="basic-data-types"></a>Grundlegende Datentypen
Da LINQ to SQL-Abfragen vor ihrer Ausführung auf dem Microsoft SQL Server in Transact-SQL übersetzt werden, unterstützt LINQ to SQL einen Großteil der integrierten Funktionen, die SQL Server für grundlegende Datentypen bereitstellt.  
  
## <a name="casting"></a>Umwandlung von Typen  
 Implizite und explizite Umwandlungen von einem CLR-Quell- in einen CLR-Zieltyp werden unterstützt, wenn in SQL Server eine ähnliche gültige Konvertierung existiert. Weitere Informationen über CLR-Umwandlung finden Sie unter [CType-Funktion](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) und [als](~/docs/csharp/language-reference/keywords/as.md). Nach der Konvertierung passen Varianten das Verhalten der durchgeführten Operationen für einen CLR-Ausdruck an das Verhalten anderer CLR-Ausdrücke an, die auf natürliche Weise dem Zieltyp zugewiesen werden. Umwandlungen sind auch im Kontext der Vererbungszuordnung übersetzbar. Objekte können in spezifischere Entitätsuntertypen umgewandelt werden, damit auf ihre untertypspezifischen Daten zugegriffen werden kann.  
  
## <a name="equality-operators"></a>Gleichheitsoperatoren  
 LINQ to SQL unterstützt die folgenden Gleichheitsoperatoren für grundlegende Datentypen in LINQ to SQL-Abfragen:  
  
-   Gleich und Ungleichheitsoperator: Gleichheits-und Ungleichheitsoperatoren werden für numerische unterstützt <xref:System.Boolean>, <xref:System.DateTime>, und <xref:System.TimeSpan> Typen. Weitere Informationen zu Visual Basic-Operatoren `=` und `<>`, finden Sie unter [Vergleichsoperatoren](~/docs/visual-basic/language-reference/operators/comparison-operators.md). Weitere Informationen zu C# Vergleichsoperatoren `==` und `!=`, finden Sie unter [==-Operator](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) und [! =-Operator](~/docs/csharp/language-reference/operators/not-equal-operator.md)bzw.  
  
-   Is-Operator: Die `IS` Operator verfügt über eine unterstützte Übersetzung, wenn Vererbungsmapping verwendet wird. Er kann anstelle der direkten Prüfung der Diskriminatorspalte verwendet werden, um festzulegen, ob ein Objekt einen bestimmten Typ aufweist. Er wird in eine Prüfung der Diskriminatorspalte übersetzt. Weitere Informationen zu den Visual Basic und C# Is-Operatoren, finden Sie unter [Is Operator](~/docs/visual-basic/language-reference/operators/is-operator.md) und [ist](~/docs/csharp/language-reference/keywords/is.md).  
  
## <a name="see-also"></a>Siehe auch
- [SQL-CLR-Typenzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
