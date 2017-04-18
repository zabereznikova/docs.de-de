---
title: Wert des Typs &quot;&lt;&quot;Typname1&quot;&gt;&quot;kann nicht konvertiert werden&quot;&lt;typename2&gt;&quot; | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
dev_langs:
- VB
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
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
ms.openlocfilehash: c973d5e2aa03d423e1dea8053946172655f08490
ms.lasthandoff: 03/13/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>Wert des Typs '&lt;"Typname1"&gt;"kann nicht konvertiert werden"&lt;typename2&gt;'
Wert des Typs '\<"Typname1" >' kann nicht konvertiert werden "\<typename2 >'. Typenkonflikt wird möglicherweise durch das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >'. Ersetzen Sie den Verweis auf "\<Filepath >" im Projekt "\<projectname1 >" durch einen Projektverweis auf '\<projectname2 >'.  
  
 Wenn ein Projekt sowohl einen Projektverweis als auch einen Dateiverweis enthält, kann der Compiler, dass ein Typ in einen anderen konvertiert werden kann nicht gewährleisten.  
  
 Der folgende Pseudocode veranschaulicht eine Situation, die diesen Fehler verursachen kann.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 Project `P1` macht einen indirekten Projektverweis über Projekt `P2` Projekt `P3`, und auch ein direkter Verweis auf `P3`. Die Deklaration von `commonObject` verwendet den Dateiverweis auf `P3`, während im Aufruf von `P2.getCommonClass` verwendet den Projektverweis `P3`.  
  
 Das Problem in diesem Fall ist, dass im Dateiverweis ein Dateipfad und-Name für die Ausgabedatei angegeben `P3` (normalerweise p3.dll), während die Projektverweise das Quellprojekt ermitteln (`P3`) nach dem Projektnamen. Aus diesem Grund der Compiler nicht garantieren, dass den Typ `P3.commonClass` demselben Quellcode über zwei unterschiedliche Verweise stammt.  
  
 Diese Situation tritt normalerweise auf, wenn Projektverweise und Dateiverweise gemeinsam. In der vorherigen Abbildung sind das Problem würde nicht auftreten, wenn `P1` erstellt einen direkten Projektverweis auf `P3` statt eines Dateiverweises.  
  
 **Fehler-ID:** BC30955  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ändern Sie den Verweis auf einen Projektverweis.  
  
## <a name="see-also"></a>Siehe auch  
 [Typumwandlungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [NIB How to: Add or Remove References By Using the Add Reference Dialog Box (Vorgehensweise: Hinzufügen und Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“)](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
