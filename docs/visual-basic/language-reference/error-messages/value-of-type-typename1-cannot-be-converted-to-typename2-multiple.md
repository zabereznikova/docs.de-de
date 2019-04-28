---
title: Der Wert vom Typ '<typename1>' kann nicht in '<typename2>' konvertiert werden (Mehrere Dateiverweise)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 58b334eb5e6db443bcfaba72729d59cb1d798e70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766817"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a>Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 >' (mehrere Dateiverweise)
Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 >'. Typenkonflikt möglicherweise aufgrund eines Dateiverweises auf '\<dateipfad1 >' im Projekt "\<projektname1 >" mit einem Dateiverweis auf "\<dateipfad2 >' im Projekt"\<projektname2 > ". Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.  
  
 In einer Situation, in denen ein Projekt mehr als eine Datei auf eine Assembly verweist, garantiert der Compiler nicht, dass es sich bei einem Typ in einen anderen konvertiert werden kann.  
  
 Jeder Dateiverweis gibt einen Pfad und Name der Ausgabedatei eines Projekts (i. d. r. eine DLL-Datei). Der Compiler garantieren nicht, dass die Ausgabedateien aus derselben Quelle stammen, oder, dass sie dieselbe Version derselben Assembly darstellen. Es kann nicht aus diesem Grund garantieren, dass die Typen in die verschiedenen Verweise desselben Typs, oder dass ein in den anderen konvertiert werden kann.  
  
 Sie können einen Einzeldatei-Verweis verwenden, wenn Sie wissen, dass die referenzierten Assemblys über dieselbe Assemblyidentität verfügen. Die *Identität der Assembly* enthält den Namen, die Version, ggf. den öffentlichen Schlüssel sowie die Kultur der Assembly. Diese Information kennzeichnet die Assembly eindeutig.  
  
 **Fehler-ID:** BC30961  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn die referenzierten Assemblys über dieselbe Assemblyidentität verfügen, entfernen Sie oder Ersetzen Sie einen der Dateiverweise, sodass nur ein einzelne Dateiverweis vorhanden ist.  
  
- Wenn die referenzierten Assemblys nicht über dieselbe Assemblyidentität verfügen, ändern Sie den Code, damit es nicht versucht, einen Typ in einem auf einen Typ in der anderen zu konvertieren.  
  
## <a name="see-also"></a>Siehe auch

- [Typkonvertierung in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
