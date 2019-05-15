---
title: Nothing und Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591341"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing und Zeichenfolgen in Visual Basic
Evaluieren Sie Visual Basic Runtime und .NET Framework `Nothing` anders als bei es geht um Zeichenfolgen.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic-Laufzeit und .NET Framework  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Die Visual Basic-Laufzeit wertet normalerweise `Nothing` als leere Zeichenfolge (""). .NET Framework jedoch nicht der Fall ist, und löst eine Ausnahme aus, wenn versucht wird, einen Zeichenfolge-Vorgang ausgeführt `Nothing`.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
