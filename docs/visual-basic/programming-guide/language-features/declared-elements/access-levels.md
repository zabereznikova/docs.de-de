---
title: "Access Levels in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "members, accessing in Visual Basic"
  - "Friend access modifier"
  - "access levels, declared elements"
  - "access levels"
  - "access modifiers"
  - "Public access modifier"
  - "Protected access modifier"
  - "Protected Friend access modifier"
  - "Private access modifier"
  - "declared elements, access level"
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Access Levels in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Die *Zugriffsebene* eines deklarierten Elements gibt an, welche Zugriffsmöglichkeiten für das Element gelten, d. h. welchem Code es gestattet ist, das Element zu lesen oder Daten in das Element zu schreiben.  Dies wird nicht nur durch die Deklaration des Elements selbst bestimmt, sondern auch durch die Zugriffsebene des Elementcontainers.  Code, der nicht auf ein Containerelement zugreifen kann, kann auch nicht auf darin enthaltene Elemente zugreifen, selbst dann nicht, wenn diese Elemente als `Public` deklariert sind.  Auf eine `Public`\-Variable in einer `Private`\-Struktur kann beispielsweise von innerhalb der Klasse zugegriffen werden, die die Struktur enthält, jedoch nicht von außerhalb dieser Klasse.  
  
## Public  
 Das [Public](../../../../visual-basic/language-reference/modifiers/public.md)\-Schlüsselwort in der Deklarationsanweisung gibt an, dass von Code an beliebiger Stelle innerhalb desselben Projekts, von anderen Projekten, die auf dieses Projekt verweisen, und von einer aus diesem Projekt erstellten Assembly aus auf die Elemente zugegriffen werden kann.  Im folgenden Codebeispiel wird eine `Public`\-Beispieldeklaration gezeigt.  
  
```  
Public Class classForEverybody  
```  
  
 Sie können `Public` nur auf Modul\-, Schnittstellen\- oder Namespaceebene verwenden.  Daher können Sie ein öffentliches Element in Quelldateien oder Namespaces bzw. innerhalb von Schnittstellen, Modulen, Klassen oder Strukturen deklarieren, jedoch nicht in Prozeduren.  
  
## Protected  
 Das [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)\-Schlüsselwort in der Deklarationsanweisung gibt an, dass auf die Elemente nur von derselben Klasse oder von einer von dieser Klasse abgeleiteten Klasse aus zugegriffen werden kann.  Im folgenden Codebeispiel wird eine `Protected`\-Beispieldeklaration gezeigt.  
  
```  
Protected Class classForMyHeirs  
```  
  
 Sie können `Protected` nur auf Klassenebene verwenden und nur dann, wenn Sie einen Member einer Klasse deklarieren.  Daher können Sie ein geschütztes Element in Klassen deklarieren, nicht jedoch in Quelldateien oder Namespaces bzw. innerhalb von Schnittstellen, Modulen, Strukturen oder Prozeduren.  
  
## Friend  
 Das [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)\-Schlüsselwort in der Deklarationsanweisung gibt an, dass von innerhalb derselben Assembly auf die Elemente zugegriffen werden kann, nicht jedoch von außerhalb der Assembly.  Im folgenden Codebeispiel wird eine `Friend`\-Beispieldeklaration gezeigt.  
  
```  
Friend stringForThisProject As String  
```  
  
 Sie können `Friend` nur auf Modul\-, Schnittstellen\- oder Namespaceebene verwenden.  Daher können Sie Friend\-Elemente in Quelldateien oder Namespaces bzw. innerhalb von Schnittstellen, Modulen, Klassen oder Strukturen deklarieren, jedoch nicht in Prozeduren.  
  
## Protected Friend  
 Wenn die Deklarationsanweisung sowohl das `Protected`\-Schlüsselwort als auch das `Friend`\-Schlüsselwort enthält, bedeutet dies, dass auf die Elemente entweder von abgeleiteten Klassen oder von innerhalb derselben Assembly bzw. von beiden aus zugegriffen werden kann.  Im folgenden Codebeispiel wird eine `Protected` `Friend`\-Beispieldeklaration gezeigt.  
  
```  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 Sie können `Protected` `Friend` nur auf Klassenebene verwenden und nur dann, wenn Sie einen Member einer Klasse deklarieren.  Daher können Sie ein geschütztes Friend\-Element in Klassen deklarieren, nicht jedoch in Quelldateien oder Namespaces bzw. innerhalb von Schnittstellen, Modulen, Strukturen oder Prozeduren.  
  
## Private  
 Das [Private](../../../../visual-basic/language-reference/modifiers/private.md)\-Schlüsselwort in der Deklarationsanweisung gibt an, dass auf die Elemente nur von innerhalb desselben Moduls, derselben Klasse oder derselben Struktur aus zugegriffen werden kann.  Im folgenden Codebeispiel wird eine `Private`\-Beispieldeklaration gezeigt.  
  
```  
Private numberForMeOnly As Integer  
```  
  
 `Private` kann nur auf Modulebene verwendet werden.  Daher können Sie ein privates Element innerhalb von Modulen, Klassen oder Strukturen deklarieren, nicht jedoch auf der Ebene von Quelldateien oder Namespaces bzw. innerhalb von Schnittstellen oder Prozeduren.  
  
 Auf Modulebene entspricht die `Dim`\-Anweisung ohne Zugriffsebenen\-Schlüsselwörter einer `Private`\-Deklaration.  Die Verwendung des `Private`\-Schlüsselworts wird jedoch empfohlen, um den Code leichter lesbar und verständlicher zu gestalten.  
  
## Zugriffsmodifizierer  
 Die Schlüsselwörter für die Angabe der Zugriffsebene werden als *Zugriffsmodifizierer* bezeichnet.  In der folgenden Tabelle werden die Zugriffsmodifizierer verglichen.  
  
|Zugriffsmodifizierer|Gewährte Zugriffsebene|Elemente, die mit dieser Zugriffsebene deklariert werden können|Deklarationskontext, in dem dieser Modifizierer verwendet werden kann|  
|--------------------------|----------------------------|---------------------------------------------------------------------|---------------------------------------------------------------------------|  
|`Public`|Uneingeschränkt:<br /><br /> Jeder Code, der ein öffentliches Element erkennen kann, kann darauf zugreifen.|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Arbeitsschritte<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Schnittstelle<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|  
|`Protected`|Abgeleitet:<br /><br /> Code innerhalb der Klasse, in der ein geschütztes Element deklariert wird, oder Code in einer von dieser Klasse abgeleiteten Klasse kann auf das Element zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Arbeitsschritte<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|  
|`Friend`|Assembly:<br /><br /> Code innerhalb der Assembly, die ein Friend\-Element deklariert, kann darauf zugreifen.|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Arbeitsschritte<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Schnittstelle<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|  
|`Protected` `Friend`|Union von `Protected` und `Friend`:<br /><br /> Code innerhalb derselben Klasse oder Assembly wie ein geschütztes Friend\-Element oder Code innerhalb einer von der Elementklasse abgeleiteten Klasse kann darauf zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Arbeitsschritte<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|  
|`Private`|Deklarationskontext:<br /><br /> Code innerhalb des Typs, der ein privates Element deklariert, einschließlich Code innerhalb von enthaltenen Typen kann auf das Element zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Arbeitsschritte<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Modul<br /><br /> Klasse<br /><br /> Struktur|  
  
## Siehe auch  
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [How to: Control the Availability of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)