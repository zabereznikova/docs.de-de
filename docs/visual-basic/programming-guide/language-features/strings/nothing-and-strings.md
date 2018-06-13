---
title: Nothing und Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d03781209f0f9b021d540bd251c6c6025ad21422
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647172"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing und Zeichenfolgen in Visual Basic
Visual Basic-Laufzeit und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] auswerten `Nothing` anders Wenn es darum geht, Zeichenfolgen.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic-Laufzeit und .NET Framework  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Visual Basic-Laufzeit wertet normalerweise `Nothing` als eine leere Zeichenfolge (""). Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] jedoch nicht der Fall ist, und löst eine Ausnahme aus, wenn versucht wird, führen Sie eine Zeichenfolgenoperation auf `Nothing`.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
