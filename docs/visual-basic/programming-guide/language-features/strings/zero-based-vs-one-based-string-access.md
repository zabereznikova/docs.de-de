---
title: Nullbasierter und. Zeichenfolge einsbasierte Zugriff in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 911f063d6ca9a3f5d88a1f50d9df7f908a488f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Nullbasierter und. Zeichenfolge einsbasierte Zugriff in Visual Basic
In diesem Thema vergleicht wie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] und [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ermöglichen den Zugriff auf die Zeichen in einer Zeichenfolge. Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] stellt immer nullbasierten Zugriff auf die Zeichen in einer Zeichenfolge bereit, wohingegen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bietet nullbasierte und einsbasierte Zugriff abhängig von der Funktion.  
  
## <a name="one-based"></a>Einsbasierte  
 Ein Beispiel für einen einsbasierten [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funktionieren, sollten Sie die `Mid` Funktion. Es akzeptiert ein Argument, das die Position des Zeichens gibt an, an der die Teilzeichenfolge gestartet wird, ab Position 1. Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode nimmt einen Index des Zeichens in die Zeichenfolge, an dem die Teilzeichenfolge beginnen, ab Position 0. Wenn Sie eine Zeichenfolge "ABCDE" verfügen, die einzelnen Zeichen werden nummeriert, 1,2,3,4,5 für die Verwendung mit der `Mid` -Funktion, aber 0,1,2,3,4 für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode.  
  
## <a name="zero-based"></a>Nullbasierte  
 Ein Beispiel für eine nullbasierte [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funktionieren, sollten Sie die `Split` Funktion. Es unterteilt eine Zeichenfolge und gibt ein Array, das die Teilzeichenfolgen enthält. Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> Methode auch unterteilt eine Zeichenfolge und gibt ein Array, das die Teilzeichenfolgen enthält. Da die `Split` Funktion und <xref:System.String.Split%2A> -Methodenrückgabe [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Arrays, müssen sie nullbasiert sein.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
