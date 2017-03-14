---
title: "Unsicherer Code und Zeiger (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Sicherheit [C#], Typsicherheit"
  - "C#-Programmiersprache, Unsicherer Code"
  - "Typsicherheit [C#]"
  - "unsafe-Schlüsselwort [C#]"
  - "Unsicherer Code [C#]"
  - "C#-Programmiersprache, Zeiger"
  - "Zeiger [C#], Informationen zu Zeigern"
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Unsicherer Code und Zeiger (C#-Programmierhandbuch)
Um Typsicherheit und Sicherheit zu gewährleisten, unterstützt C\# standardmäßig keine Zeigerarithmetik.  Mit dem [unsafe](../../../csharp/language-reference/keywords/unsafe.md)\-Schlüsselwort können Sie jedoch einen unsicheren Kontext definieren, in dem Zeiger verwendet werden können.  Weitere Informationen zu Zeigern finden Sie unter dem Thema [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
> [!NOTE]
>  In der Common Language Runtime \(CLR\) wird unsicherer Code als nicht überprüfbarer Code bezeichnet.  Unsicherer Code in C\# ist nicht zwangsläufig gefährlich. Es handelt sich vielmehr um Code, dessen Sicherheit nicht durch die CLR überprüft werden kann.  Die CLR führt deshalb unsicheren Code nur dann aus, wenn er sich innerhalb einer vollständig vertrauenswürdigen Assembly befindet.  Wenn Sie unsicheren Code verwenden, sind Sie dafür verantwortlich, dass der Code keine Sicherheitsrisiken oder Zeigerfehler einführt.  
  
## Übersicht über unsicheren Code  
 Unsicherer Code weist die folgenden Eigenschaften auf:  
  
-   Methoden, Typen und Codeblöcke können als unsicher definiert werden.  
  
-   In einigen Fällen kann unsicherer Code möglicherweise die Leistung einer Anwendung steigern, indem die Überprüfungen der Arraygrenzen entfernt werden.  
  
-   Unsicherer Code ist erforderlich, wenn systemeigene Funktionen aufgerufen werden, die Zeiger erfordern.  
  
-   Durch unsicheren Code werden Sicherheits\- und Stabilitätsrisiken eingeführt.  
  
-   Damit unsicherer Code in C\# kompiliert wird, muss die Anwendung mit [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.  
  
## Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:  
  
-   [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [Puffer fester Größe](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [Unsicher](../../../csharp/language-reference/keywords/unsafe.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)