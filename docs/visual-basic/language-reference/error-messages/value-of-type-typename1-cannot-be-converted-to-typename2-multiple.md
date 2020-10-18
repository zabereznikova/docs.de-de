---
title: Der Wert vom Typ '<typename1>' kann nicht in '<typename2>' konvertiert werden (Mehrere Dateiverweise)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 23c051e57014d7479d1c1c522b1a8da1ead52c19
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161386"
---
# <a name="bc30961-value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a>BC30961: der Wert des Typs "" \<typename1> kann nicht in " \<typename2> " konvertiert werden (mehrere Datei Verweise).

Der Wert vom Typ "" \<typename1> kann nicht in " \<typename2> " konvertiert werden. Typen Konflikt kann durch das Mischen eines Datei Verweises auf " \<filepath1> " in Projekt "" \<projectname1> mit einem Datei Verweis auf " \<filepath2> " in Projekt "" verursacht werden \<projectname2> . Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.

 In einer Situation, in der ein Projekt mehr als einen Datei Verweis auf eine Assembly durchführt, kann der Compiler nicht garantieren, dass ein Typ in einen anderen konvertiert werden kann.

 Jeder Datei Verweis gibt einen Dateipfad und-Namen für die Ausgabedatei eines Projekts an (in der Regel eine DLL-Datei). Der Compiler kann nicht garantieren, dass die Ausgabedateien aus derselben Quelle stammen oder dass Sie dieselbe Version derselben Assembly darstellen. Daher kann nicht sichergestellt werden, dass die Typen in den verschiedenen verweisen denselben Typ aufweisen oder dass Sie in einen anderen konvertiert werden können.

 Sie können einen einzelnen Datei Verweis verwenden, wenn Sie wissen, dass die referenzierten Assemblys die gleiche Assemblyidentität aufweisen. Die *Assemblyidentität* enthält den Assemblynamen, die Version, den öffentlichen Schlüssel, sofern vorhanden, und die Kultur. Diese Information kennzeichnet die Assembly eindeutig.

 **Fehler-ID:** BC30961

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn die Assemblys, auf die verwiesen wird, dieselbe Assemblyidentität aufweisen, entfernen oder ersetzen Sie einen der Datei Verweise, sodass es nur einen einzigen Datei Verweis gibt.

- Wenn die Assemblys, auf die verwiesen wird, nicht die gleiche Assemblyidentität aufweisen, ändern Sie den Code so, dass er nicht versucht, einen Typ in einen Typ in einen anderen Typ zu konvertieren.

## <a name="see-also"></a>Siehe auch

- [Typkonvertierung in Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
