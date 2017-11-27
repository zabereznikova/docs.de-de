---
title: Ein Wert vom Typ &#39; &lt;Typname1&gt;&#39; kann nicht konvertiert werden, um &#39;&lt; Typname2&gt;&#39; (Mehrere Dateiverweise)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords: BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc6138c7a7ca7d50a56fdd1f536e8d2dc3462a08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>Ein Wert vom Typ &#39; &lt;Typname1&gt;&#39; kann nicht konvertiert werden, um &#39;&lt; Typname2&gt;&#39; (Mehrere Dateiverweise)
Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 > ". Typenkonflikt möglicherweise aufgrund eines Dateiverweises auf "\<dateipfad1 >' in-Projekt"\<projektname1 > "mit einem Dateiverweis auf"\<dateipfad2 >' in-Projekt "\<projektname2 >". Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.  
  
 In einer Situation, in denen ein Projekt mehr als einen Dateiverweis auf eine Assembly erstellt, wird, kann der Compiler nicht garantieren, einem Typ in einen anderen konvertiert werden kann.  
  
 Jeder Dateiverweis gibt einen Dateipfad und einen Namen für die Ausgabedatei eines Projekts (in der Regel eine DLL-Datei). Der Compiler kann nicht garantieren, dass die Ausgabedateien aus der gleichen Quelle stammen oder dass sie die gleiche Version derselben Assembly darstellen. Es kann keine somit sicherstellen, dass die Typen in den verschiedenen verweisen identisch sind, oder auch, dass eine in den anderen konvertiert werden kann.  
  
 Wenn Sie wissen, dass die betreffenden Assemblys der gleichen Identität der Assembly, können Sie einen einzelnen Dateiverweis verwenden. Die *Identität der Assembly* enthält den Namen, die Version, ggf. den öffentlichen Schlüssel sowie die Kultur der Assembly. Diese Information kennzeichnet die Assembly eindeutig.  
  
 **Fehler-ID:** BC30961  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die betreffenden Assemblys der gleichen Identität der Assembly verfügen, entfernen Sie oder Ersetzen Sie eines der Dateiverweise, sodass nur ein einzelne Dateiverweis vorhanden ist.  
  
-   Wenn die referenzierten Assemblys nicht die Identität der gleichen Assembly verfügen, ändern Sie den Code, damit er nicht versucht, einen Typ in einem auf einen Typ in den anderen zu konvertieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Konvertierungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)  
 [NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
