---
title: "Gewusst wie: Konvertieren zwischen Legacycodierungen und Unicode (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Konvertierungen [C#], Vorgänger der Unicode-Codierung"
  - "Zeichenfolgen [C#], Konvertieren zwischen Codierungen"
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Konvertieren zwischen Legacycodierungen und Unicode (C#-Programmierhandbuch)
In C\# werden alle Zeichenfolgen im Arbeitsspeicher als Unicode \(UTF\-16\) codiert.  Wenn Sie Daten aus einem Speicher in ein `string`\-Objekt abrufen, werden die Daten automatisch in UTF\-16 konvertiert.  Falls die Daten lediglich ASCII\-Werte von 0 bis 127 enthalten, ist für die Konvertierung kein zusätzlicher Aufwand erforderlich.  Falls der Quelltext jedoch erweiterte ASCII\-Bytewerte \(128 bis 255\) enthält, werden die erweiterten Zeichen standardmäßig entsprechend der aktuellen Codeseite interpretiert.  Um festzulegen, dass der Quelltext entsprechend einer anderen Codeseite interpretiert werden soll, verwenden Sie die <xref:System.Text.Encoding?displayProperty=fullName>\-Klasse, wie im folgenden Beispiel dargestellt.  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie eine Textdatei, die in 8\-Bit\-ASCII codiert wurde, konvertiert und der Quelltext entsprechend der Windows\-Codeseite 737 interpretiert wird.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/CSRefStrings/Strings.cs#34)]  
  
## Siehe auch  
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)