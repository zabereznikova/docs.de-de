---
title: Nullbasierter und Eins Zeichenfolge Zugriff in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6cd2cab888bf336151ed26968119431f4ffc75f4
ms.lasthandoff: 03/13/2017

---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Nullbasierter und Eins Zeichenfolge Zugriff in Visual Basic
In diesem Thema wird wie [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] und [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] ermöglichen den Zugriff auf die Zeichen in einer Zeichenfolge. Die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] stellt immer nullbasierten Zugriff auf die Zeichen in einer Zeichenfolge bereit, während die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] nullbasierten oder&1;-basierten Zugriff, abhängig von der Funktion enthält.  
  
## <a name="one-based"></a>Eins  
 Ein Beispiel für eine&1;-basierte [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funktionieren, sollten Sie die `Mid` Funktion. Ein Argument, das die Position angibt, an der die Teilzeichenfolge mit der Position 1 beginnt beginnt, dauert. Die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>-Methode erhält einen Index des Zeichens in der Zeichenfolge, an der die Teilzeichenfolge beginnen, beginnt mit der Position 0.</xref:System.String.Substring%2A?displayProperty=fullName> Wenn Sie eine Zeichenfolge "ABCDE" verfügen, die einzelne Zeichen werden nummeriert, 1,2,3,4,5 für die Verwendung mit der `Mid` -Funktion, aber 0,1,2,3,4 für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=fullName>Methode.</xref:System.String.Substring%2A?displayProperty=fullName>  
  
## <a name="zero-based"></a>Nullbasierte  
 Ein Beispiel für ein nullbasiertes [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funktionieren, sollten Sie die `Split` Funktion. Er teilt eine Zeichenfolge und gibt ein Array, das die Teilzeichenfolgen enthält. Die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName>Methode auch eine Zeichenfolge und gibt ein Array, das die Teilzeichenfolgen enthält.</xref:System.String.Split%2A?displayProperty=fullName> Da die `Split` Funktion und <xref:System.String.Split%2A>Methode [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Arrays, müssen sie nullbasiert sein.</xref:System.String.Split%2A>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:System.String.Substring%2A></xref:System.String.Substring%2A>   
 <xref:System.String.Split%2A></xref:System.String.Split%2A>   
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
