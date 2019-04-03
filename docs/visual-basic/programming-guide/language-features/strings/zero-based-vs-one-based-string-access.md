---
title: Nullbasierter und 1-basierter Zeichenfolgenzugriff in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a6ceb10d4a3cb9463551d8c85375ddbbb607ffdc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830330"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Nullbasierter und 1-basierter Zeichenfolgenzugriff in Visual Basic
Dieses Thema vergleicht, wie Visual Basic und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ermöglichen den Zugriff auf die Zeichen in einer Zeichenfolge. Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] stellt immer nullbasierte Zugriff auf die Zeichen in einer Zeichenfolge bereit, während Visual Basic nullbasierter und 1-basierte Zugriff, abhängig von der Funktion zur Verfügung stellt.  
  
## <a name="one-based"></a>1-basierte  
 Erwägen Sie für ein Beispiel für eine 1-basierte Visual Basic-Funktion, die `Mid` Funktion. Es dauert ein Argument, das die Position des Zeichens gibt an, an der die Teilzeichenfolge gestartet wird, ab Position 1. Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode akzeptiert einen Index des Zeichens in der Zeichenfolge, an dem die Teilzeichenfolge beginnen, werden, beginnend mit der Position 0. Wenn Sie eine Zeichenfolge "ABCDE" verfügen, die einzelnen Zeichen werden nummeriert, 1,2,3,4,5 für die Verwendung mit der `Mid` -Funktion, aber 0,1,2,3,4). für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode.  
  
## <a name="zero-based"></a>Nullbasierte  
 Erwägen Sie für ein Beispiel für eine nullbasierte Visual Basic-Funktion, die `Split` Funktion. Es unterteilt eine Zeichenfolge und gibt ein Array mit Teilzeichenfolgen zurück. Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> Methode auch unterteilt eine Zeichenfolge und gibt ein Array mit Teilzeichenfolgen zurück. Da die `Split` Funktion und <xref:System.String.Split%2A> -Methodenrückgabe [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Arrays, müssen sie nullbasiert sein.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
