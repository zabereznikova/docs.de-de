---
title: "Unicode (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Unicode"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Unicode, external references"
  - "Declare statement, marshaling strings"
  - "Unicode keyword"
  - "Unicode, marshaling strings"
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Unicode (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass Visual Basic unabhängig vom Namen der externen Prozedur, die deklariert wird, alle Zeichenfolgen in Unicode\-Werte marshallen soll.  
  
 Wenn eine Prozedur aufgerufen wird, die außerhalb des Projekts definiert wurde, hat der Visual Basic\-Compiler keinen Zugriff auf bestimmet Informationen, die zum korrekten Aufrufen der Prozedur erforderlich sind.  Dies umfasst Informationen über den Speicherort der Prozedur, ihre Identifikationsmerkmale, ihre Aufrufsequenz und ihren Rückgabetyp sowie den von ihr für Zeichenfolgen verwendeten Zeichensatz.  Die [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese notwendigen Informationen zur Verfügung.  
  
 Im `charsetmodifier`\-Teil der `Declare`\-Anweisung werden Zeichensatzinformationen bereitgestellt, mit denen Zeichenfolgen bei einem externen Prozeduraufruf gemarshallt werden.  Der Abschnitt hat auch Einfluss darauf, wie Visual Basic die externe Datei nach dem externen Prozedurnamen durchsucht.  Der Modifizierer `Unicode` legt fest, dass Visual Basic alle Zeichenfolgen in Unicode\-Werte marshallen und die Prozedur nachschlagen soll, ohne während der Suche ihren Namen zu ändern.  
  
 Wenn kein Zeichensatzmodifizierer angegeben ist, wird standardmäßig `Ansi` verwendet.  
  
## Hinweise  
 Der `Unicode`\-Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare\-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## Hinweise für Entwickler intelligenter Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## Siehe auch  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)   
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)