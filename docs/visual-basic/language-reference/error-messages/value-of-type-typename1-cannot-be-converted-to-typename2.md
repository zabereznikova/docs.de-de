---
title: Der Wert vom Typ "<typename1>" kann nicht zu "<typename2>" konvertiert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 67cb8ac602437474f35c89c9aecf66fbf40c91c9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875041"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a>Der Wert vom Typ "\<typename1>" kann nicht zu "\<typename2>" konvertiert werden.

Der Wert vom Typ "" \<typename1> kann nicht in " \<typename2> " konvertiert werden. Typen Konflikt kann durch das Mischen eines Datei Verweises mit einem Projekt Verweis auf die Assembly "" verursacht werden \<assemblyname> . Ersetzen Sie den Datei Verweis auf " \<filepath> " im Projekt "" \<projectname1> durch einen Projekt Verweis auf " \<projectname2> ".  
  
 In einer Situation, in der ein Projekt sowohl einen Projekt Verweis als auch einen Datei Verweis erstellt, kann der Compiler nicht garantieren, dass ein Typ in einen anderen konvertiert werden kann.  
  
 Der folgende Pseudo Code veranschaulicht eine Situation, in der dieser Fehler generiert werden kann.  
  
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
  
 Project `P1` führt einen indirekten Projekt Verweis über Project `P2` to Project `P3` und auch einen direkten Datei Verweis auf aus `P3` . In der Deklaration von `commonObject` wird der Datei Verweis auf verwendet `P3` , während der-Befehl von `P2.getCommonClass` den Projekt Verweis auf verwendet `P3` .  
  
 Das Problem in dieser Situation besteht darin, dass der Datei Verweis einen Dateipfad und-Namen für die Ausgabedatei (in der `P3` Regel p3.dll) angibt, während die Projekt Verweise das Quell Projekt ( `P3` ) nach Projektname identifizieren. Aus diesem Grund kann der Compiler nicht garantieren, dass der Typ `P3.commonClass` aus dem gleichen Quellcode durch die beiden unterschiedlichen Verweise stammt.  
  
 Diese Situation tritt in der Regel auf, wenn Projekt Verweise und Datei Verweise gemischt werden. In der obigen Abbildung tritt das Problem nicht auf, wenn `P1` ein direkter Projekt Verweis auf `P3` anstelle eines Datei Verweises erstellt wurde.  
  
 **Fehler-ID:** BC30955  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Ändern Sie den Datei Verweis in einen Projekt Verweis.  
  
## <a name="see-also"></a>Weitere Informationen

- [Typkonvertierung in Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
