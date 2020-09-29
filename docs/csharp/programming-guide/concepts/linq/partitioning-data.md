---
title: Partitionieren von Daten (C#)
description: Erfahren Sie, wie Sie Daten in LINQ partitionieren. Sehen Sie sich eine Abbildung mit den Ergebnissen von Partitionierungsvorgängen an.
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: 31beacd672addb3eb38ade8f2bf9cfae25f4d27a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176265"
---
# <a name="partitioning-data-c"></a>Partitionieren von Daten (C#)

Partitionieren in LINQ bezieht sich auf den Vorgang, bei dem eine Eingabesequenz in zwei Abschnitte unterteilt wird, ohne die Elemente dabei neu anzuordnen, und bei dem anschließend einer der Abschnitte zurückzugeben wird.  
  
 Die folgende Abbildung zeigt das Ergebnis von drei verschiedenen Partitionierungsvorgängen einer Zeichensequenz. Der erste Vorgang gibt die ersten drei Elemente in der Sequenz zurück. Der zweite Vorgang überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück. Der dritte Vorgang überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.  
  
 ![Abbildung zu drei LINQ-Partitionierungsvorgängen.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 Die Methoden des Standardabfrageoperators, die Sequenzen partitionieren, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="operators"></a>Operatoren  
  
|Name des Operators|Beschreibung|C#-Abfrageausdruckssyntax|Weitere Informationen|  
|-------------------|-----------------|---------------------------------|----------------------|  
|Skip|Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz|Nicht zutreffend.|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Überspringt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element die Bedingung nicht erfüllt|Nicht zutreffend.|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Übernimmt Elemente bis zu einer angegebenen Position in einer Sequenz|Nicht zutreffend.|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Übernimmt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element der Bedingung nicht erfüllt|Nicht zutreffend.|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))](./standard-query-operators-overview.md)
