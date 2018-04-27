---
title: Typ &#39; &lt;Typename&gt; &#39; ist nicht definiert
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7c3efbcabf1e40c7f550b5f54d16e697561cf82c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Typ &#39; &lt;Typename&gt; &#39; ist nicht definiert
Die Anweisung machte Verweis auf einen Typ, der nicht definiert wurde. Sie können einen Typ wie z. B. in einer deklarationsanweisung definieren `Enum`, `Structure`, `Class`, oder `Interface`.  
  
 **Fehler-ID:** BC30002  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Typdefinition und dessen Verweis beide die gleiche Schreibweise verwenden.  
  
-   Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist. Wenn der Typ befindet sich in einem anderen Modul und deklariert wurde, z. B. `Private`, verschieben Sie die Typdefinition in das Verweismodul oder deklarieren Sie es `Public`.  
  
-   Stellen Sie sicher, dass der Namespace des Typs nicht innerhalb des Projekts neu definiert wird. Wenn dies der Fall, verwenden Sie die `Global` Schlüsselwort, um den Typnamen vollständig zu qualifizieren. Wenn ein Projekt einen Namespace mit dem Namen definiert, z. B. `System`, die <xref:System.Object?displayProperty=nameWithType> Typ kann nicht zugegriffen werden, es sei denn, es ist vollqualifizierte mit der `Global` Schlüsselwort: `Global.System.Object`.  
  
-   Wenn der Typ definiert ist, aber die Objekt- oder Typbibliothek, die in der sie definiert ist nicht registriert, klicken Sie in Visual Basic, auf **Verweis hinzufügen** auf die **Projekt** Menü, und wählen Sie dann das entsprechende Objekt oder Typbibliothek.  
  
-   Stellen Sie sicher, dass der Typ in einer Assembly, die das Ziel .NET Framework-Profil gehört. Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Siehe auch  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
