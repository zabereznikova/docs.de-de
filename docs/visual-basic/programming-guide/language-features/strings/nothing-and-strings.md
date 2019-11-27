---
title: Nothing und Zeichenfolgen
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: dfc43748d0754f0a6a29763c42ab82d9937f89f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344292"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing und Zeichenfolgen in Visual Basic
Die Visual Basic-Laufzeit und die .NET Framework werden `Nothing` anders ausgewertet, wenn Sie Zeichen folgen sind.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic Runtime und die .NET Framework  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Die Visual Basic Runtime wertet `Nothing` in der Regel als leere Zeichenfolge ("") aus. Der .NET Framework jedoch nicht, und löst eine Ausnahme aus, wenn versucht wird, einen Zeichen folgen Vorgang auf `Nothing`auszuführen.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
