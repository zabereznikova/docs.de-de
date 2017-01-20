---
title: "Auto (Visual Basic) | Microsoft Docs"
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
  - "vb.Auto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Auto keyword, external references"
  - "Declare statement, marshaling strings"
  - "Auto keyword"
  - "Auto keyword, marshaling strings"
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Auto (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass Visual Basic Zeichenfolgen entsprechend den .NET\-Framework\-Regeln auf der Grundlage des externen Namens der deklarierten externen Prozedur marshallen soll.  
  
 Wenn Sie eine außerhalb Ihres Projekts definierte Prozedur aufrufen, hat der Visual Basic\-Compiler keinen Zugriff auf die erforderlichen Informationen zum ordnungsgemäßen Aufrufen der Prozedur.  Dies umfasst Informationen über den Speicherort der Prozedur, ihre Identifikationsmerkmale, ihre Aufrufsequenz und ihren Rückgabetyp sowie den von ihr für Zeichenfolgen verwendeten Zeichensatz.  Die [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese notwendigen Informationen zur Verfügung.  
  
 Der `charsetmodifier`\-Abschnitt in der `Declare`\-Anweisung stellt Informationen über den Zeichensatz bereit, die benötigt werden, um Zeichenfolgen bei einem Aufruf der externen Prozedur zu marshallen.  Der Abschnitt hat auch Einfluss darauf, wie Visual Basic die externe Datei nach dem externen Prozedurnamen durchsucht.  Der `Auto`\-Modifizierer gibt an, dass Visual Basic Zeichenfolgen entsprechend den .NET\-Framework\-Regeln marshallen soll, dass der Basiszeichensatz der Laufzeitplattform ermittelt und eventuell der externe Prozedurname geändert werden soll, wenn die anfängliche Suche fehlschlägt.  Weitere Informationen finden Sie im Abschnitt "Zeichensatz" unter [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Wenn kein Zeichensatzmodifizierer angegeben ist, wird standardmäßig `Ansi` verwendet.  
  
## Hinweise  
 Der `Auto`\-Modifizierer kann im folgenden Kontext verwendet werden:  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## Hinweise für Entwickler intelligenter Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## Siehe auch  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)   
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)