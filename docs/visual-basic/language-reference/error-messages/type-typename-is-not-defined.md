---
title: Der Typ "<typename>" ist nicht definiert.
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 3c22e6a5199bd52cb9fae66a15a66ac9ce095e81
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872198"
---
# <a name="type-typename-is-not-defined"></a>Der Typ "\<typename>" ist nicht definiert.

Die-Anweisung hat einen Verweis auf einen Typ vorgenommen, der nicht definiert wurde. Sie können einen Typ in einer Deklarations Anweisung definieren `Enum` , z `Structure` . b.,, `Class` oder `Interface` .  
  
 **Fehler-ID:** BC30002  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Stellen Sie sicher, dass für die Typdefinition und deren Verweis dieselbe Schreibweise verwendet wird.  
  
- Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist. Wenn der Typ z. b. in einem anderen Modul ist und deklariert wurde `Private` , verschieben Sie die Typdefinition in das verweisende Modul, oder deklarieren Sie Sie `Public` .  
  
- Stellen Sie sicher, dass der Namespace des Typs nicht innerhalb des Projekts neu definiert wird. Ist dies der Fall, verwenden Sie das `Global` Schlüsselwort, um den Typnamen vollständig zu qualifizieren. Wenn ein Projekt beispielsweise einen Namespace mit dem Namen definiert `System` , <xref:System.Object?displayProperty=nameWithType> kann nicht auf den Typ zugegriffen werden, es sei denn, er ist mit dem `Global` Schlüsselwort voll qualifiziert: `Global.System.Object` .  
  
- Wenn der Typ definiert ist, aber die Objektbibliothek oder die Typbibliothek, in der er definiert ist, nicht in Visual Basic registriert ist, klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** , und wählen Sie dann die entsprechende Objektbibliothek oder Typbibliothek aus.  
  
- Stellen Sie sicher, dass der Typ in einer Assembly enthalten ist, die Teil des Ziel .NET Framework Profils ist. Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Weitere Informationen

- [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [Enum-Anweisung](../statements/enum-statement.md)
- [Structure Statement](../statements/structure-statement.md)
- [Class-Anweisung](../statements/class-statement.md)
- [Interface-Anweisung](../statements/interface-statement.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
