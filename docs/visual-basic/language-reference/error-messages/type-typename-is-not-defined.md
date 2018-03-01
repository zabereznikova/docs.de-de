---
title: Geben Sie &#39; &lt;Typename&gt;&#39; ist nicht definiert
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68eb37f43600c51dc9117c3785a12e3c8ede1965
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Geben Sie &#39; &lt;Typename&gt;&#39; ist nicht definiert
Die Anweisung machte Verweis auf einen Typ, der nicht definiert wurde. Sie können einen Typ wie z. B. in einer deklarationsanweisung definieren `Enum`, `Structure`, `Class`, oder `Interface`.  
  
 **Fehler-ID:** BC30002  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Typdefinition und dessen Verweis beide die gleiche Schreibweise verwenden.  
  
-   Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist. Wenn der Typ befindet sich in einem anderen Modul und deklariert wurde, z. B. `Private`, verschieben Sie die Typdefinition in das Verweismodul oder deklarieren Sie es `Public`.  
  
-   Stellen Sie sicher, dass der Namespace des Typs nicht innerhalb des Projekts neu definiert wird. Wenn dies der Fall, verwenden Sie die `Global` Schlüsselwort, um den Typnamen vollständig zu qualifizieren. Wenn ein Projekt einen Namespace mit dem Namen definiert, z. B. `System`, die <xref:System.Object?displayProperty=nameWithType> Typ kann nicht zugegriffen werden, es sei denn, es ist vollqualifizierte mit der `Global` Schlüsselwort: `Global.System.Object`.  
  
-   Wenn der Typ definiert ist, aber nicht die Objekt- oder Typbibliothek, die in der sie definiert registriert [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], klicken Sie auf **Verweis hinzufügen** auf die **Projekt** Menü, und wählen Sie dann das entsprechende Objekt oder Typbibliothek.  
  
-   Stellen Sie sicher, dass der Typ in einer Assembly, die das Ziel .NET Framework-Profil gehört. Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Siehe auch  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
