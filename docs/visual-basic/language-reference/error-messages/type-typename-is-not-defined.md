---
title: Typ &quot;&lt;Typename&gt;&quot; ist nicht definiert | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 09aa7c535fd5e17ddcd0e743fb5ec17ebadd4f7d
ms.lasthandoff: 03/13/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Typ '&lt;Typename&gt;' ist nicht definiert
Die Anweisung hat auf einen Typ verwiesen, die nicht definiert wurde. Sie können einen Typ wie z. B. in einer deklarationsanweisung definieren `Enum`, `Structure`, `Class`, oder `Interface`.  
  
 **Fehler-ID:** BC30002  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Typdefinition und dessen Verweis derselben Schreibweise verwenden.  
  
-   Stellen Sie sicher, dass die Typdefinition für den Verweis zugänglich ist. Wenn der Typ in einem anderen Modul und deklariert wurde, z. B. `Private`, verschieben Sie die Typdefinition in das Verweismodul oder deklarieren Sie es `Public`.  
  
-   Stellen Sie sicher, dass der Namespace des Typs nicht innerhalb des Projekts neu definiert wird. Wenn dies der Fall, verwenden die `Global` -Schlüsselwort verwenden, um den Typnamen vollständig zu qualifizieren. Wenn ein Projekt einen Namespace mit dem Namen definiert, z. B. `System`, die <xref:System.Object?displayProperty=fullName>Typ kann nicht zugegriffen werden, es sei denn, es mit vollqualifiziert ist die `Global` Schlüsselwort: `Global.System.Object`.</xref:System.Object?displayProperty=fullName>  
  
-   Wenn der Typ definiert ist, aber die Objekt- oder Typbibliothek, in der er definiert ist, ist nicht registriert [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], klicken Sie auf **Verweis hinzufügen** auf der **Projekt** Menü, und wählen Sie dann die geeignete Objekt- oder Typbibliothek.  
  
-   Stellen Sie sicher, dass der Typ in einer Assembly, die Teil der entsprechenden .NET Framework-Profil ist. Weitere Informationen finden Sie unter [Problembehandlung bei .NET Framework-Zielversionsfehlern](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Siehe auch  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Verwalten von Verweisen in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)
