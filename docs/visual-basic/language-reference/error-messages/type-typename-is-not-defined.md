---
title: Der Typ "<typename>" ist nicht definiert.
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: c2675d61307d92da1710368668f43af3559060a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032096"
---
# <a name="type-typename-is-not-defined"></a>Typ "\<Typname >' ist nicht definiert.
Die Anweisung hat auf einen Typ verwiesen, die nicht definiert wurde. Sie können einen Typ wie z. B. in einer deklarationsanweisung definieren `Enum`, `Structure`, `Class`, oder `Interface`.  
  
 **Fehler-ID:** BC30002  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Stellen Sie sicher, dass es sich bei der Definition des Typs und dessen Verweis beide die gleiche Schreibweise verwenden.  
  
- Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist. Wenn der Typ in einem anderen Modul und deklariert wurde, z. B. `Private`, verschieben Sie die Typdefinition in der Verweismodul oder deklarieren sie `Public`.  
  
- Stellen Sie sicher, dass der Namespace des Typs in Ihrem Projekt nicht neu definiert wird. Wenn es sich handelt, verwenden Sie die `Global` Schlüsselwort, um den Namen vollständig qualifizieren. Wenn ein Projekt einen Namespace mit dem Namen definiert, z. B. `System`, <xref:System.Object?displayProperty=nameWithType> Typ kann nicht zugegriffen werden, es sei denn, es mit vollqualifiziert ist die `Global` Schlüsselwort: `Global.System.Object`.  
  
- Wenn der Typ definiert ist, aber die Objekt- oder Typbibliothek, die in der sie definiert ist nicht registriert, klicken Sie in Visual Basic auf **Verweis hinzufügen** auf die **Projekt** Menü, und wählen Sie dann das entsprechende Objekt oder Typbibliothek.  
  
- Stellen Sie sicher, dass der Typ in einer Assembly, die das Ziel .NET Framework-Profil gehört. Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Siehe auch

- [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
