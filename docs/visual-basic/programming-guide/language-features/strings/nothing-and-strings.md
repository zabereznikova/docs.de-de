---
title: Nothing und Zeichenfolgen in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce9f81f23f50e38f6b1ad5e638e8c6ac026e992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing und Zeichenfolgen in Visual Basic
Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Common Language Runtime und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] auswerten `Nothing` anders Wenn es darum geht, Zeichenfolgen.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic-Laufzeit und .NET Framework  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Laufzeit wertet normalerweise `Nothing` als eine leere Zeichenfolge (""). Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] jedoch nicht der Fall ist, und löst eine Ausnahme aus, wenn versucht wird, führen Sie eine Zeichenfolgenoperation auf `Nothing`.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
