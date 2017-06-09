---
title: "Gewusst wie: Ausf&#252;hren von grundlegenden Zeichenfolgenbearbeitungen in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zeichenfolgen [.NET Framework], Beispiele"
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Ausf&#252;hren von grundlegenden Zeichenfolgenbearbeitungen in .NET Framework
Im folgenden Beispiel werden einige der Methoden verwendet, die in den Themen unter [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md) erörtert wurden. Es wird eine Klasse erstellt, durch die Zeichenfolgen in ähnlicher Weise wie in einer realen Anwendung bearbeitet werden.  Die `MailToData`\-Klasse speichert Namen und Adresse einer Person in separaten Eigenschaften und bietet eine Möglichkeit, die Felder `City`, `State` und `Zip` in einer einzigen Zeichenfolge zu kombinieren und für den Benutzer anzuzeigen.  Darüber hinaus ermöglicht es die Klasse dem Benutzer, Stadt, Bundesland und Postleitzahl in einer einzigen Zeichenfolge einzugeben. Die Anwendung analysiert diese einzelne Zeichenfolge automatisch und fügt die geeigneten Informationen in die entsprechende Eigenschaft ein.  
  
 Der Einfachheit halber wird in diesem Beispiel eine Konsolenanwendung mit einer Befehlszeilenschnittstelle verwendet.  
  
## Beispiel  
 [!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
 [!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
 Wenn der vorangehende Code ausgeführt wird, wird der Benutzer aufgefordert, Namen und Adresse einzugeben.  Die Anwendung legt die Informationen in den entsprechenden Eigenschaften ab und zeigt die Informationen erneut an. Dazu wird eine einzelne Zeichenfolge erstellt, in der Stadt, Bundesland und Postleitzahl aufgeführt sind.  
  
## Siehe auch  
 [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)