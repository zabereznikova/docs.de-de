---
title: Der Wert vom Typ '<typename1>' kann nicht zu '<typename2>' konvertiert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 027cccc9ad406d5bc2fd686ddeb4c674dc8f3c90
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621200"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a>Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 >'
Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 >'. {Typenkonflikt beim wird möglicherweise durch das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >'. Den Dateiverweis, ersetzen Sie die "\<" FilePath ">" in Projekt "\<projektnamen1 >' mit einem Projektverweis auf"\<projektname2 > ".  
  
 In einer Situation, in denen ein Projekt sowohl einen Projektverweis als auch ein Dateiverweis erstellt, garantiert der Compiler nicht, dass es sich bei einem Typ in einen anderen konvertiert werden kann.  
  
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
  
 Projekt `P1` indirekte Projekt verweist auf Projekt `P2` Projekt `P3`, und auch einen direkten Verweis auf `P3`. Die Deklaration von `commonObject` verwendet den Dateiverweis auf `P3`, während im Aufruf von `P2.getCommonClass` verwendet den Projektverweis `P3`.  
  
 Das Problem in diesem Fall ist, dass es sich bei der Dateiverweis gibt an, einen Pfad und Namen für die Ausgabedatei `P3` (normalerweise p3.dll), während die Projektverweise auf das Quellprojekt ermitteln (`P3`) nach Projektname. Aus diesem Grund der Compiler nicht garantieren, dass den Typ `P3.commonClass` stammt aus der gleiche Quellcode über zwei unterschiedliche Verweise.  
  
 Diese Situation tritt in der Regel auf, wenn Projektverweise und Dateiverweise kombiniert werden. In der vorhergehenden Abbildung können das Problem würde nicht auftreten, wenn `P1` vorgenommen einen direkten Projektverweis auf `P3` anstelle eines Dateiverweises.  
  
 **Fehler-ID:** BC30955  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Den Dateiverweis, einen Projektverweis zu ändern.  
  
## <a name="see-also"></a>Siehe auch

- [Typkonvertierung in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
