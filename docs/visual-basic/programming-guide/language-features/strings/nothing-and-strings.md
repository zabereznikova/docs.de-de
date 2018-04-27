---
title: Nothing und Zeichenfolgen in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d7693e712884a500495e4573900e7d9a049c2879
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing und Zeichenfolgen in Visual Basic
Visual Basic-Laufzeit und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] auswerten `Nothing` anders Wenn es darum geht, Zeichenfolgen.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic-Laufzeit und .NET Framework  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Visual Basic-Laufzeit wertet normalerweise `Nothing` als eine leere Zeichenfolge (""). Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] jedoch nicht der Fall ist, und löst eine Ausnahme aus, wenn versucht wird, führen Sie eine Zeichenfolgenoperation auf `Nothing`.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
