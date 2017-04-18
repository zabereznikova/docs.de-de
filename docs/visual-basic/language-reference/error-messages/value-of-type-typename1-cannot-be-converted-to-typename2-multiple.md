---
title: Wert des Typs &quot;&lt;&quot;Typname1&quot;&gt;&quot;kann nicht konvertiert werden&quot;&lt;typename2&gt;&quot;(mehrere Dateiverweise) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 732291ce9c4b83bb9fc7e83fbbc2a8da9748db59
ms.lasthandoff: 03/13/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>Wert des Typs '&lt;"Typname1"&gt;"kann nicht konvertiert werden"&lt;typename2&gt;"(mehrere Dateiverweise)
Wert des Typs '\<"Typname1" >' kann nicht konvertiert werden "\<typename2 >'. Typenkonflikt möglicherweise aufgrund eines Dateiverweises auf '\<filepath1 > "im Projekt"\<projectname1 >' mit einem Verweis auf "\<filepath2 >" im Projekt "\<projectname2 >'. Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.  
  
 Ein Projekt mehr als ein Verweis auf eine Assembly enthält, kann der Compiler, dass ein Typ in einen anderen konvertiert werden kann nicht gewährleisten.  
  
 Jeder Dateiverweis gibt einen Dateipfad und-Name für die Ausgabedatei eines Projekts (in der Regel eine DLL-Datei). Der Compiler kann nicht garantieren, dass die Ausgabedateien aus derselben Quelle stammen, oder dass sie die gleiche Version derselben Assembly darstellen. Es kann nicht deshalb sicherstellen, dass die Typen in den verschiedenen verweisen, vom gleichen Typ sind, oder auch, dass eine in den anderen konvertiert werden kann.  
  
 Sie können einen einzigen Dateiverweis verwenden, wenn Sie wissen, dass die referenzierten Assemblys dieselbe Assemblyidentität. Die *Identität der Assembly* enthält den Namen, die Version, ggf. den öffentlichen Schlüssel sowie die Kultur der Assembly. Diese Information kennzeichnet die Assembly eindeutig.  
  
 **Fehler-ID:** BC30961  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die referenzierten Assemblys dieselbe Assemblyidentität verfügen, entfernen Sie oder Ersetzen Sie eines der Dateiverweise, sodass nur ein einzelne Dateiverweis vorhanden ist.  
  
-   Wenn die referenzierten Assemblys nicht dieselbe Assemblyidentität verfügen, ändern Sie den Code, damit es nicht versucht, einen Typ in einem auf einen Typ in den anderen zu konvertieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Typumwandlungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [NIB How to: Add or Remove References By Using the Add Reference Dialog Box (Vorgehensweise: Hinzufügen und Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“)](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
