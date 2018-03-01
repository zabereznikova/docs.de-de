---
title: "Ungültiger Prüfsummenwert, keine hexadezimalen Ziffern oder ungerade Anzahl von hexadezimalen Ziffern."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1158742c8eaa51bcbb5607795f16ae6c2b570db4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a>Ungültiger Prüfsummenwert, keine hexadezimalen Ziffern oder ungerade Anzahl von hexadezimalen Ziffern.
Ein Prüfsummenwert enthält ungültige hexadezimale Ziffern oder hat eine ungerade Anzahl an Ziffern.  
  
 Wenn ASP.NET eine Visual Basic-Quelldatei (Dateierweiterung .vb) erstellt, berechnet es die Prüfsumme und platziert sie in einer ausgeblendeten Quelldatei, die mit `#externalchecksum` gekennzeichnet wird. Ein Benutzer, der eine VB-Datei generiert, hat die Möglichkeit, dies selbst zu übernehmen, doch dieser Prozess sollte lieber intern ausgeführt werden.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42033  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Wenn ASP.NET die Visual Basic-Quelldatei generiert, starten Sie den Projektbuild neu.  
  
2.  Wenn diese Warnung auch nach einem Neustart ausgegeben wird, installieren Sie ASP.NET neu, und führen Sie den Vorgang mit dem Build erneut aus.  
  
3.  Wenn auch dann die Warnung weiterhin besteht oder wenn Sie nicht ASP.NET verwenden, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch  
 [ASP.NET Overview (Übersicht über ASP.NET)](https://msdn.microsoft.com/library/4w3ex9c2.aspx)  
 [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
