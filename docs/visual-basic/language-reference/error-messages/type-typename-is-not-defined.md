---
title: "Type &#39;&lt;typename&gt;&#39; is not defined | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30002"
  - "bc30002"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30002"
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Type &#39;&lt;typename&gt;&#39; is not defined
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Die Anweisung erstellte einen Verweis auf einen Typ, der nicht definiert wurde.  Sie können einen Typ, z. B. `Enum`, `Structure`, `Class` oder `Interface`, in einer Deklarationsanweisung definieren.  
  
 **Fehler\-ID:** BC30002  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Schreibweise der Typdefinition und des Verweises übereinstimmen.  
  
-   Stellen Sie sicher, dass der Verweis auf die Typdefinition zugreifen kann.  Wenn sich der Typ z. B. in einem anderen Modul befindet und als `Private` deklariert wurde, verschieben Sie die Typdefinition in das Verweismodul oder deklarieren Sie sie als `Public`.  
  
-   Stellen Sie sicher, dass der Namespace des Typs innerhalb des Projekts neu definiert wurde.  Verwenden Sie in diesem Fall das `Global`\-Schlüsselwort, um den Typnamen vollständig zu qualifizieren.  Wenn z. B. ein Projekt einen Namespace mit dem Namen `System` definiert, kann der <xref:System.Object?displayProperty=fullName>\-Typ erst aufgerufen werden, wenn er mit dem `Global`\-Schlüsselwort vollständig qualifiziert wurde: `Global.System.Object`.  
  
-   Wenn der Typ zwar definiert, die Objekt\- oder Typbibliothek, in der er definiert wurde, in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] jedoch nicht registriert ist, klicken Sie im Menü **Projekt** auf **Verweis hinzufügen**, und wählen Sie anschließend die geeignete Objekt\- oder Typbibliothek aus.  
  
-   Stellen Sie sicher, dass der Typ in einer Assembly enthalten ist, die Teil des als Ziel festgelegten .NET Framework\-Profils ist.  Weitere Informationen finden Sie unter [Troubleshooting .NET Framework Targeting Errors](/visual-studio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## Siehe auch  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Verwalten von Verweisen in einem Projekt](/visual-studio/ide/managing-references-in-a-project)