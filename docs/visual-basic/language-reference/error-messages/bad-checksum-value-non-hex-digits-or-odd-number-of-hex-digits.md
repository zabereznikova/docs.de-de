---
title: "Bad checksum value, non hex digits or odd number of hex digits | Microsoft Docs"
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
  - "bc42033"
  - "vbc42033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42033"
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Bad checksum value, non hex digits or odd number of hex digits
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Prüfsummenwert enthält ungültige hexadezimale Ziffern oder hat eine ungerade Anzahl an Ziffern.  
  
 Wenn ASP.NET eine Visual Basic\-Quelldatei \(Dateierweiterung .vb\) erstellt, berechnet es die Prüfsumme und platziert sie in einer ausgeblendeten Quelldatei, die mit `#externalchecksum` gekennzeichnet wird.  Ein Benutzer, der eine VB\-Datei generiert, hat die Möglichkeit, dies selbst zu übernehmen, doch dieser Prozess sollte lieber intern ausgeführt werden.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen zum Ausblenden von Warnungen oder zum Bearbeiten von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42033  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn ASP.NET die Visual Basic\-Quelldatei generiert, starten Sie den Projektbuild neu.  
  
2.  Wenn diese Warnung auch nach einem Neustart ausgegeben wird, installieren Sie ASP.NET neu, und führen Sie den Vorgang mit dem Build erneut aus.  
  
3.  Wenn auch dann die Warnung weiterhin besteht oder wenn Sie nicht ASP.NET verwenden, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## Siehe auch  
 [ASP.NET Overview](../Topic/ASP.NET%20Overview.md)   
 [Sprechen Sie mit uns](/visual-studio/ide/talk-to-us)