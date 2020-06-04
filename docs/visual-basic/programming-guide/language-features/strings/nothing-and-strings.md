---
title: Nothing und Zeichenfolgen
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 392de45b0ee1688224f3e8170b0144f1acdb0912
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360565"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing und Zeichenfolgen in Visual Basic
Die Visual Basic Runtime und die .NET Framework werden unter `Nothing` schiedlich ausgewertet, wenn Sie Zeichen folgen sind.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic Runtime und die .NET Framework  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Die Visual Basic-Laufzeit wird in der Regel `Nothing` als leere Zeichenfolge ("") ausgewertet. Der .NET Framework jedoch nicht, und löst eine Ausnahme aus, wenn versucht wird, einen Zeichen folgen Vorgang für auszuführen `Nothing` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in Zeichenfolgen in Visual Basic](introduction-to-strings.md)
