---
title: "Ansi (Visual Basic) | Microsoft Docs"
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
  - "vb.Ansi"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Declare statement, marshaling strings"
  - "ANSI, Visual Basic"
  - "ANSI"
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ansi (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Legt fest, dass Visual Basic alle Zeichenfolgen unabhängig von dem Namen der deklarierten externen Prozedur als ANSI\-Werte \(American National Standards Institute\) marshallen soll.  
  
 Wenn Sie eine außerhalb Ihres Projekts definierte Prozedur aufrufen, hat der Visual Basic\-Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen.  Dies umfasst Informationen über den Speicherort der Prozedur, ihre Identifikationsmerkmale, ihre Aufrufsequenz und ihren Rückgabetyp sowie den von ihr für Zeichenfolgen verwendeten Zeichensatz.  Die [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese notwendigen Informationen zur Verfügung.  
  
 Der `charsetmodifier`\-Abschnitt in der `Declare`\-Anweisung stellt Informationen über den Zeichensatz bereit, die benötigt werden, um Zeichenfolgen bei einem Aufruf der externen Prozedur zu marshallen.  Der Abschnitt hat auch Einfluss darauf, wie Visual Basic die externe Datei nach dem externen Prozedurnamen durchsucht.  Mit dem `Ansi`\-Modifizierer wird angegeben, dass Visual Basic alle Zeichenfolgen als ANSI\-Werte marshallen und die Prozedur suchen soll, ohne deren Namen während der Suche zu ändern.  
  
 Wenn kein Zeichensatzmodifizierer angegeben ist, wird standardmäßig `Ansi` verwendet.  
  
## Hinweise  
 Der `Ansi`\-Modifizierer kann im folgenden Kontext verwendet werden:  
  
 [Declare\-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## Hinweise für Entwickler intelligenter Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## Siehe auch  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)