---
title: "Grundlegende Datentypen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Grundlegende Datentypen
Da LINQ to SQL\-Abfragen vor ihrer Ausführung auf dem Microsoft SQL Server in Transact\-SQL übersetzt werden,  unterstützt LINQ to SQL einen Großteil der integrierten Funktionen, die SQL Server für grundlegende Datentypen bereitstellt.  
  
## Umwandlung von Typen  
 Implizite und explizite Umwandlungen von einem CLR\-Quell\- in einen CLR\-Zieltyp werden unterstützt, wenn in SQL Server eine ähnliche gültige Konvertierung existiert.  Weitere Informationen über CLR\-Umwandlung finden Sie unter [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md) \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) und [as](../Topic/as%20\(C%23%20Reference\).md).  Nach der Konvertierung passen Umwandlungen das Verhalten der durchgeführten Vorgänge für einen CLR\-Ausdruck an das Verhalten anderer CLR\-Ausdrücke an, die auf natürliche Weise dem Zieltyp zugewiesen werden. Umwandlungen sind auch im Kontext der Vererbungszuordnung übersetzbar.  Objekte können in spezifischere Entitätsuntertypen umgewandelt werden, damit auf ihre untertypspezifischen Daten zugegriffen werden kann.  
  
## Gleichheitsoperatoren  
 LINQ to SQL unterstützt die folgenden Gleichheitsoperatoren für grundlegende Datentypen in LINQ to SQL\-Abfragen:  
  
-   Gleichheits\- und Ungleichheitsoperator: Gleichheits\- und Ungleichheitsoperatoren werden für numerische <xref:System.Boolean>\-, <xref:System.DateTime>\- und <xref:System.TimeSpan>\-Typen unterstützt.  Weitere Informationen zu [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\-Operatoren `=` und `<>` finden Sie unter [Comparison Operators](../Topic/Comparison%20Operators%20\(Visual%20Basic\).md). Weitere Informationen zu C\#\-Vergleichsoperatoren `==` und `!=` finden Sie unter [Operator \=\=](../Topic/==%20Operator%20\(C%23%20Reference\).md) und [Operator \!\=](../Topic/!=%20Operator%20\(C%23%20Reference\).md).  
  
-   "Is"\-Operator: Der `IS`\-Operator verfügt über eine unterstützte Übersetzung, wenn Vererbungsmapping verwendet wird.  Er kann anstelle der direkten Prüfung der Diskriminatorspalte verwendet werden, um festzulegen, ob ein Objekt einen bestimmten Typ aufweist. Er wird in eine Prüfung der Diskriminatorspalte übersetzt.  Weitere Informationen über die "Is"\-Operatoren in Visual Basic und C\# finden Sie unter [Is Operator](../Topic/Is%20Operator%20\(Visual%20Basic\).md) und [is](../Topic/is%20\(C%23%20Reference\).md).  
  
## Siehe auch  
 [SQL CLR\-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)   
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)