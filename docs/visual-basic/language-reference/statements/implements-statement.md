---
title: "Implements Statement | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Implements"
  - "Implements"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Implements statement, syntax"
  - "Implements statement"
  - "interface implementation, Implements statement"
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Implements Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt eine oder mehrere Schnittstellen oder Schnittstellenmember an, die in der umgebenden Klassen\- oder Strukturdefinition implementiert werden müssen.  
  
## Syntax  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## Teile  
 `interfacename`  
 Erforderlich.  Eine Schnittstelle, deren Eigenschaften, Prozeduren und Ereignisse von entsprechenden Membern in der Klasse oder Struktur implementiert werden.  
  
 `interfacemember`  
 Erforderlich.  Der Member einer Schnittstelle, der implementiert wird.  
  
## Hinweise  
 Eine Schnittstelle ist eine Auflistung von Prototypen, die die von der Schnittstelle gekapselten Member \(Eigenschaften, Prozeduren und Ereignisse\) darstellt.  Schnittstellen enthalten nur die Deklarationen für Member. Klassen und Strukturen implementieren diese Member.  Weitere Informationen finden Sie unter [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Die `Implements`\-Anweisung muss unmittelbar auf die `Class`\-Anweisung oder die `Structure`\-Anweisung folgen.  
  
 Wenn Sie eine Schnittstelle implementieren, müssen Sie alle in der Schnittstelle deklarierten Member implementieren.  Sie erhalten einen Syntaxfehler, wenn Sie einen der Member auslassen.  Um einen einzelnen Member zu implementieren, geben Sie das [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)\-Schlüsselwort \(das nicht mit der `Implements`\-Anweisung identisch ist\) an, wenn Sie den Member in der Klasse oder Struktur deklarieren.  Weitere Informationen finden Sie unter [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Klassen können [Private](../../../visual-basic/language-reference/modifiers/private.md)\-Implementierungen von Eigenschaften und Prozeduren verwenden, der Zugriff auf diese Member ist jedoch nur möglich, wenn eine Instanz der implementierenden Klasse in eine Variable umgewandelt wird, die als Typ der Schnittstelle deklariert wird.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Implements`\-Anweisung verwendet wird, um Member einer Schnittstelle zu implementieren.  Im Beispiel wird die Schnittstelle `ICustomerInfo` mit einem Ereignis, einer Eigenschaft und einer Prozedur definiert.  Die `customerInfo`\-Klasse implementiert alle Member, die in der Schnittstelle definiert sind.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 Beachten Sie, dass die `customerInfo`\-Klasse die `Implements`\-Anweisung in einer eigenen Quellcodezeile verwendet, um anzugeben, dass die Klasse alle Member der `ICustomerInfo`\-Schnittstelle implementiert.  Anschließend verwendet jeder Member der Klasse das `Implements`\-Schlüsselwort als Teil seiner Memberdeklaration, um anzugeben, dass er diesen Schnittstellenmember implementiert.  
  
## Beispiel  
 In den folgenden beiden Prozeduren wird veranschaulicht, wie Sie die im vorherigen Beispiel implementierte Schnittstelle verwenden können.  Zum Testen der Implementierung fügen Sie dem Projekt diese Prozeduren hinzu und rufen die `testImplements`\-Prozedur auf.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## Siehe auch  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)